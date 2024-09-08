<template>
<!-- Component 만드는 법 : *.vue 로 끝나는 파일을 생성 후, 기본 tag들을 생성 후 , <template>에 축약할 html 요소를 추가 -->
    <div class="discount">
        <h4>지금 결제하면 20% 할인</h4>
    </div>
</template>

<script>
export default {
    name : 'discountComponent'
}
</script>

<style>

.discount{
  background :#eee;
  padding:10px;
  margin : 10px;
  border-radius: 5px;
}
</style>