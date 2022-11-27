<script lang="ts">
import './button.css'
import { createEventDispatcher } from 'svelte'

export const backgroundColor = ''
export const size = 'medium'
export const label = ''
const style = backgroundColor ? `background-color: ${backgroundColor}` : ''

const dispatch = createEventDispatcher()

function onClick(event) {
  dispatch('click', event)
}
</script>

<button
  type="button"
  class="{['storybook-button', `storybook-button--${size}`].join(' ')}"
  style="{style}"
  on:click="{onClick}">
  {label}
</button>
