<template>
  <div class="menu-btn">
    <div class="menu-btn__burger"></div>
  </div>
</template>

<script scoped>
export default {
  name: 'Burger',
  methods: {
    clickActionListener: function() {
      const menuBtn = document.querySelector('.menu-btn');
      let menuOpen = false;
      menuBtn.addEventListener('click', () => {
        if(!menuOpen) {
          menuBtn.classList.add('open');
          menuOpen = true;
        } else {
          menuBtn.classList.remove('open');
          menuOpen = false;
        }
      });
    }
  }
}
</script>

<style scoped>
.menu-btn {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 80px;
  height: 80px;
  cursor: pointer;
  transition: all .5s ease-in-out;
  /* border: 3px solid #fff; */
}
.menu-btn__burger {
  width: 50px;
  height: 6px;
  background: #5a5a5a;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(255,101,47,.2);
  transition: all .6s ease-in-out;
}
.menu-btn__burger::before,
.menu-btn__burger::after {
  content: '';
  position: absolute;
  width: 50px;
  height: 6px;
  background: #5a5a5a;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(255,101,47,.2);
  transition: all .5s ease-in-out;
}
.menu-btn__burger::before {
  transform: translateY(-16px);
}
.menu-btn__burger::after {
  transform: translateY(16px);
}
/* ANIMATION */
.menu-btn.open .menu-btn__burger {
  transform: translateX(-50px);
  background: transparent;
  box-shadow: none;
}
.menu-btn.open .menu-btn__burger::before {
  transform: rotate(45deg) translate(35px, -35px);
}
.menu-btn.open .menu-btn__burger::after {
  transform: rotate(-45deg) translate(35px, 35px);
}
</style>