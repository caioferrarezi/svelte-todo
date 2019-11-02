<script>
  export let todos = []
</script>

<style>
  .c-todos {
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    list-style: none;
  }

  .c-todos__item {
    position: relative;
    display: block;
    width: 100%;
    padding: 3rem;
    font-size: 2.4rem;
    font-weight: lighter;
    background-color: #ffffff;
    border-top: .3rem dotted var(--light-color);
  }

  .c-todos__item::after {
    content: '';
    display: block;
    width: .5rem;
    position: absolute;
    top: 20%;
    bottom: 20%;
    left: -.25rem;
    background-color: var(--primary-color);
    transition: all .15s ease-in-out;
  }

  .c-todos__item:hover::after {
    top: 0;
    bottom: 0;
  }
</style>

{#if todos.length}
  <ul class="c-todos">
    {#each todos as todo (todo.id)}
      <li class="c-todos__item">
        {todo.text}
      </li>
    {/each}
  </ul>
{/if}
