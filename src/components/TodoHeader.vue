<template>
  <!-- Html  -->
<div> 
  <!-- compoenent 당 꼭  하나씩만 root tag가 존재해야함. : component 구분을 위해   -->
  <header>
    <h1>TODO it~!</h1>
  </header>
</div>
</template>

<style scoped>
 /*
 스타일링 시 상위 컴포넌트의 스타일링을 하위 컴포넌트가 상송 받는 속성을 무시하고, 
 오직 해당 컴포넌트 내에서만 스타일을 사용하기 위해 <style scoped> 를 사용한다.  
 */
/* css */
h1 {
  color: #2F3B52;
  font-weight: 900;
  /* font의 크기에 따라 배율이 정해지는 rem 단위 */
  margin: 2.5rem 0 1.5rem; 
}
</style>