<script lang="ts">
  import './button.css'
  import { createEventDispatcher } from 'svelte'

  export let backgroundColor: string
  export let size = 'medium'
  export let label = ''

  let style = backgroundColor ? `background-color: ${backgroundColor}` : ''

  const dispatch = createEventDispatcher()

  function onClick(event) {
    dispatch('click', event)
  }
</script>

<button
  type="button"
  class={['storybook-button', `storybook-button--${size}`].join(' ')}
  {style}
  on:click={onClick}
>
  {label}
</button>
