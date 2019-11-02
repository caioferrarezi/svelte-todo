<script>
  export let todoItem = {}

  function handleFormSubmit(e) {
    const form = e.target
    const formData = new FormData(form)

    e.preventDefault()

    todoItem = {
      id: generateTodoItemId(),
      text: formData.get('todo'),
      checked: false
    }

    form.reset()
  }

  function generateTodoItemId() {
    return Math.random().toString(36).substr(2, 9)
  }
</script>

<style>
  .c-todo-form {
    display: block;
    width: 80%;
    height: 6rem;
    margin: auto;
  }

  .c-todo-form__input {
    display: block;
    width: 100%;
    color: var(--dark-color);
    text-align: center;
    font-size: 2.4rem;
    font-weight: lighter;
    line-height: 6rem;
    height: 6rem;
    padding: 0 1.6rem;
    border: 0;
    box-shadow: 0 0 0 .1rem var(--light-color);
    transition: box-shadow .15s ease-in-out, background-color .1s ease-in-out;
  }

  .c-todo-form__input:focus {
    background-color: var(--light-color);
    box-shadow: 0 .8rem 1.6rem rgba(0, 0, 0, .1);
  }
</style>

<form
  action="#"
  class="c-todo-form"
  method="POST"
  on:submit={handleFormSubmit}>

  <input
    type="text"
    name="todo"
    placeholder="Do the groceries..."
    class="c-todo-form__input">
</form>
