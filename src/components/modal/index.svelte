<script>
  import { each } from "svelte/internal";
  import { tick, onMount, createEventDispatcher } from "svelte";

  export let showModal; // boolean\
  export let showSaveButton = true;
  export let heightSize;
  export let saveButtonName = "Save";
  export let closeButtonName = "Close";

  let dialog;
  $: console.log("in heightSize: ", heightSize);
  $: if (dialog && showModal) {
    dialog.showModal();
  }

  const dispatch = createEventDispatcher();

  const clickButton = (e) => {
    dispatch("clickButton", e);
  };

  const closeButton = (e) => {
    dialog.close();
    dispatch("closeButton", e);
  };
  export const offShowModal = () => {
    new Promise((resolve, reject) => {
      console.log("offfShowwmodal");
      showModal = false;

      resolve(dialog.close());
    });
  };

  var r = document.querySelector(":root");
  r.style.setProperty("--height-dialog", heightSize);
</script>

<dialog
  id="white-modal"
  bind:this={dialog}
  on:close={() => (showModal = false)}
  on:click|self={() => dialog.close()}
>
  <div on:click|stopPropagation>
    <slot name="content" />

    <slot />

    <div class="form-style">
      <div style="display:flex">
        {#if showSaveButton}
          <div on:click={clickButton}>
            <button>{saveButtonName}</button>
          </div>
        {/if}
        <div>
          <button on:click={closeButton}>Close</button>
        </div>
      </div>
    </div>
  </div>
</dialog>

<style>
  :root {
    --height-dialog: 100px;
  }
  dialog {
    max-width: 32em;
    border-radius: 0.2em;
    border: none;
    padding: 0;
    min-height: 250px;
    height: var(--height-dialog);
    width: 100%;
  }
  dialog::backdrop {
    background: rgba(0, 0, 0, 0.3);
  }
  dialog > div {
    padding: 1em;
  }
  dialog[open] {
    animation: zoom 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
  }
  @keyframes zoom {
    from {
      transform: scale(0.95);
    }
    to {
      transform: scale(1);
    }
  }
  dialog[open]::backdrop {
    animation: fade 0.2s ease-out;
  }
  @keyframes fade {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
  button {
    display: block;
  }

  .form-style {
    bottom: 10px;
    position: absolute;
    right: 10px;
  }
</style>
