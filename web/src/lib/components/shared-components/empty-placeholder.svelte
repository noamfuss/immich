<script lang="ts">
  import empty1Url from '$lib/assets/empty-1.svg';

  export let actionHandler: undefined | (() => unknown) = undefined;
  export let text = '';
  export let alt = '';

  let hoverClasses = 'hover:bg-immich-primary/5 dark:hover:bg-immich-dark-primary/25 hover:cursor-pointer';
</script>

{#if actionHandler}
  <!-- svelte-ignore a11y-no-static-element-interactions -->
  <div
    on:click={actionHandler}
    on:keydown={actionHandler}
    class="border dark:border-immich-dark-gray {hoverClasses} m-auto mt-10 flex w-[50%] flex-col place-content-center place-items-center rounded-3xl bg-gray-50 p-5 dark:bg-immich-dark-gray"
  >
    <img src={empty1Url} {alt} width="500" draggable="false" />
    <p class="text-immich-text-gray-500 text-center dark:text-immich-dark-fg">{text}</p>
  </div>
{:else}
  <div
    class="m-auto mt-10 flex w-[50%] flex-col place-content-center place-items-center rounded-3xl border bg-gray-50 p-5 dark:border-immich-dark-gray dark:bg-immich-dark-gray"
  >
    <img src={empty1Url} {alt} width="500" draggable="false" />
    <p class="text-immich-text-gray-500 text-center dark:text-immich-dark-fg">{text}</p>
  </div>
{/if}
