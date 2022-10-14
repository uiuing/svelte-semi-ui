<script>
  import './button.css';
  import { createEventDispatcher } from 'svelte';

  export let primary = false;
  export let backgroundColor;
  export let size = 'medium';
  export let label = '';

  let mode = primary ? 'storybook-button--primary' : 'storybook-button--secondary';

  let style = backgroundColor ? `background-color: ${backgroundColor}` : '';

  const dispatch = createEventDispatcher();

  function onClick(event) {
    dispatch('click', event);
  }
</script>

<button
  type="button"
  class={['storybook-button', `storybook-button--${size}`, mode].join(' ')}
  {style}
  on:click={onClick}>
  {label}
</button>
