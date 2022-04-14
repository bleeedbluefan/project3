<template>
<div id="app">
  <div id="menu">

    <div id="side1">
      <button id="vacation-button">     
        <router-link to="/test">
          <div class="menu-item browse">
            <p>Test Yourself</p>
          </div>
        </router-link>
      </button>
          <div class="repo">
            <a href="https://github.com/bleeedbluefan/project3">Github Repository</a>
          </div>
    </div>
    
    <div id="brand">
      <router-link to="/">
        <img src="/images/globe.jpg">
      </router-link>
    </div>
    <div id="side2">
      <button id="past-button">     
        <router-link to="/cart">
          <div class="menu-item browse">
            <p>States You Know</p>
          </div>
        </router-link>
      </button>
    </div>
  </div>
  <router-view />
</div>
</template>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;

}

.repo {
  margin-left: 10px;
}
#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "side1 brand side2";
  margin-bottom: 50px;

}

#menu a {
  color: #060d6d;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#side1 {
  display: flex;
  justify-content: flex-start;
  padding-bottom: 290px;
}

#side2 {
  display: flex;
  justify-content: flex-end;
  padding-bottom: 290px;
}

#brand img {
  height: 300px;
}

</style>