<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link" href="#" @click="goToPage('shoppingList')">Liste de course</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#" @click="goToPage('recipes')">Recettes</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#" @click="goToPage('ingredients')">Ingrédients</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#" @click="goToPage('addIngredientV2')">Ingrédients V2</a>
          </li>
        </ul>
      </div>
      <MyLogin></MyLogin>
    </div>
  </nav>
</template>

<script>
import MyLogin from './MyLogin.vue';

export default ({
  components: {
    MyLogin,
  },
  emits: ['switchPage'],
  setup(_, context) {
    const goToPage = (page) => {
      context.emit('switch-page', page);
    };

    return {
      goToPage,
    };
  },
});
</script>
