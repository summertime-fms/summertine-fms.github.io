<template>
    <div class="wrapper">
      <div class="todo-inner">
        <h1 class="title">Todo List</h1>
        <button class="button" type="button">Add</button>
        <TodoList :todos="todos" />
      </div>

      <span class="copyright">© 2022. Author Name</span>
    </div>
</template>

<script>
import TodoList from '@/components/TodoList.vue';
export default {
  name: 'App',
  components: {
    TodoList
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Купить слона',
          description: 'lorem lorem lorem',
          completed: false
        },
        {
          id: 2,
          title: 'Купить слона',
          description: 'lorem lorem lorem',
          completed: false
        },
        {
          id: 3,
          title: 'Купить тигра',
          description: 'lorem lorem lorem',
          completed: false
        },
        {
          id: 4,
          title: 'Купить носорога',
          description: 'lorem lorem lorem',
          completed: false
        },
        {
          id: 5,
          title: 'Купить котика',
          description: 'lorem lorem lorem',
          completed: false
        },
        {
          id: 6,
          title: 'Купить котика',
          description: 'lorem lorem lorem',
          completed: false
        },
        {
          id: 7,
          title: 'Купить котика',
          description: 'lorem lorem lorem',
          completed: false
        },
        {
          id: 8,
          title: 'Купить котика',
          description: 'lorem lorem lorem',
          completed: false
        },
        {
          id: 9,
          title: 'Купить котика',
          description: 'lorem lorem lorem',
          completed: false
        }
      ]
    }
  }
}
</script>

<style>
  :root {
    --trans: 0.155s cubic-bezier(.215,.61,.355,1);
    --orange: #FF8469;
    --gray: #4F5565;
    --white: #ffffff;
    --gradient: radial-gradient(50% 50% at 50% 50%, #252E42 0%, #161C2E 100%);

    --main-font: "Montserrat", "Arial", sans-serif;

  }

  @font-face {
    font-family: 'Montserrat';
    src: local('Montserrat'),
    url('~@/assets/fonts/Montserrat-Regular.woff2') format('woff2');
    font-weight: 400;
    font-style: normal;
    font-display: swap;
  }

  @font-face {
    font-family: 'Montserrat';
    src: local('Montserrat'),
    url('~@/assets/fonts/Montserrat-Medium.woff2') format('woff2');
    font-weight: 500;
    font-style: normal;
    font-display: swap;
  }

  @font-face {
    font-family: 'Montserrat';
    src: local('Montserrat'),
    url('~@/assets/fonts/Montserrat-Bold.woff2') format('woff2');
    font-weight: 700;
    font-style: normal;
    font-display: swap;
  }

  .visually-hidden {
    position: absolute;
    white-space: nowrap;
    width: 1px;
    height: 1px;
    overflow: hidden;
    border: 0;
    padding: 0;
    clip: rect(0 0 0 0);
    clip-path: inset(50%);
    margin: -1px;
  }

  *, ::after, ::before {
    box-sizing: inherit;
  }

  html {
    font-size: 16px;
    box-sizing: border-box;
  }

  body {
    margin: 0;
    padding: 0;
    font-weight: 400;
    font-family: var(--main-font);
    background: var(--gradient);
  }

  .wrapper {
    position: relative;
    max-width: 420px;
    width: 100%;
    margin: 0 auto;
    margin-bottom: 50px;
    padding: 0 15px;
  }

  .wrapper::before,
  .wrapper::after {
    content: '';

    display: block;
    position: absolute;
    border-radius: 20px;
  }

  .wrapper::before {
    top: -35px;
    left: 16px;
    z-index: 1;
    width: 86%;
    height: 85px;
    background: linear-gradient(180deg, #4F5565 0%, #000000 53.65%);
    transform: matrix(1, -0.09, 0.06, 1, 0, 0);
  }

  .wrapper::after {
    top: -20px;
    z-index: 2;
    width: 90%;
    height: 67px;
    background: linear-gradient(180deg, #31394D 0%, #091739 100%);
    transform: matrix(1, -0.05, 0.03, 1, 0, 0);
  }

  .todo-inner {
    position: relative;
    z-index: 5;
    max-height: 540px;

    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto auto;
    align-items: center;
    grid-row-gap: 30px;
    margin-top: 100px;
    margin-bottom: 31px;
    padding: 30px;
    background: #252E42;
    box-shadow: 0px 14px 34px rgba(0, 0, 0, 0.25);
    border-radius: 20px 0px 40px;
  }

  .todo-inner::after {
    content: "";
    position: absolute;
    z-index: 10;
    bottom: 0;
    width: 100%;
    height: 75px;
    background: linear-gradient(180deg, rgba(37, 46, 66, 0) 0%, #252E42 67.19%);;
  }

  .title {
    margin: 0;
    font-size: 1.75rem;
    color: var(--white);
  }

  @media(max-width: 428px) {
    .title {
      font-size: 1.5rem;
    }
  }

  .button {
    display: flex;
    align-items: center;
    justify-content: center;
    grid-column: 2/3;
    justify-self: end;
    min-height: 27px;
    border-radius: 7px;
    background-color: var(--orange);
    padding: 5px 10px;
    border: 0;

    font-weight: 500;
    font-size: 14px;
    text-transform: uppercase;
    line-height: 1.21;
    color: var(--white);
    transition: background-color var(--trans), color var(--trans);
    cursor: pointer;
  }

  .button:hover {
    background-color: cornflowerblue;
  }

  .copyright {
    display: block;
    color: var(--gray);
    font-weight: 500;
    text-align: center;
  }
</style>
