<template>
  <button class="btn ripple">
    <slot/>
  </button>
</template>

<script>
export default {
  name: 'ui-button'
}
</script>

<style>
  [type='submit'],
  [type='reset'],
  [type='button'],
  button {
    font: inherit;
    line-height: normal;
    overflow: visible;
    padding: 0;
    cursor: pointer;
    user-select: none;
    color: inherit;
    border: 0;
    appearance: initial;
  }

  button::-moz-focus-inner {
    padding: 0;
    border: 0;
  }

  .btn {
    font-size: 1em;
    font-weight: 400;
    position: relative;
    display: inline-flex;
    align-items: center;
    align-self: center;
    flex: 0 0 auto;
    justify-content: center;
    padding: 0.8em 1.6em;
    user-select: none;
    transition: all 300ms cubic-bezier(0.25, 0.8, 0.5, 1) 0ms, color 0s ease;
    vertical-align: top;
    text-decoration: none;
    color: inherit;
    border-radius: 0;
    outline: 0;
    background-color: var(--gray-color-600);
    justify-self: center;
    touch-action: manipulation;
    will-change: box-shadow;

    &:disabled {
      cursor: not-allowed;
      pointer-events: none;
      color: rgba(0, 0, 0, 0.26);
      background-color: rgba(0, 0, 0, 0.12);
      box-shadow: none;
    }

    &:not([class~='ripple']):hover {
      background-image: linear-gradient(
        to right,
        rgba(255, 255, 255, 0.1),
        rgba(255, 255, 255, 0.1)
      );
    }

    &:not([class~='ripple']):active {
      background-image: initial;
    }

    &[class~='box-shadow-1']:active {
      box-shadow: 0 5px 5px -3px rgba(0, 0, 0, 0.2),
      0 8px 10px 1px rgba(0, 0, 0, 0.14), 0 3px 14px 2px rgba(0, 0, 0, 0.12);
    }
  }

  .btn--flat {
    color: inherit;
    border: none;
    background: transparent;

    &:hover {
      background-image: linear-gradient(
        to right,
        rgba(0, 0, 0, 0.1),
        rgba(0, 0, 0, 0.1)
      );
    }

    &:disabled {
      background: none;
    }
  }

  .btn--ellipse {
    padding: 0.9em;
    border-radius: 50%;
  }

  .btn--outline {
    color: inherit;
    border: 1px solid;
    background: transparent;
  }

  .btn--preloader {
    pointer-events: none;

    .preloader {
      display: initial;
    }
  }

</style>
