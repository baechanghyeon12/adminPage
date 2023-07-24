<template>
  <div class="bg_black" v-if="$store.state.modalFlg && $store.state.listNumber == 0">
    <div class="bg_white">
        <hr>
        <h2 style="color: red;">{{$store.state.userNumber.length}}명의 회원을 선택하셨습니다.<br>선택하신 회원들이 모두 탈퇴됩니다.<br>탈퇴회원들은 되돌릴수 없습니다.<br>탈퇴 시키시겠습니까??</h2>
        <hr>
      <button @click="$store.commit('modalClose');">확인</button>
      <button @click="$store.commit('modalClose'); $store.dispatch('getUserStateList',1);">닫기</button>
    </div>
  </div>
  <div class="bg_black" v-if="$store.state.modalFlg && $store.state.listNumber == 1">
    <div class="bg_white">
        <hr>
        <h2 style="color: red;">{{$store.state.userNumber.length}}명의 회원을 선택하셨습니다.<br>선택하신 회원들이 모두 탈퇴됩니다.<br>탈퇴회원들은 되돌릴수 없습니다.<br>탈퇴 시키시겠습니까??</h2>
        <hr>
      <button @click="$store.commit('modalClose');">확인</button>
      <button @click="$store.commit('modalClose');">닫기</button>
    </div>
  </div>
  <div class="bg_black" v-if="$store.state.modalFlg && $store.state.listNumber == 2">
    <div class="bg_white">
        <hr>
        <h2 style="color: red;">{{$store.state.stateNumber.length}}명의 회원을 선택하셨습니다.<br>선택하신 회원들이 모두 탈퇴됩니다.<br>탈퇴회원들은 되돌릴수 없습니다.<br>탈퇴 시키시겠습니까??</h2>
        <hr>
      <button @click="$store.commit('modalClose');">확인</button>
      <button @click="$store.commit('modalClose');">닫기</button>
    </div>
  </div>
</template>
<script>
export default {
    name: 'Modal',
}
</script>
<style>
    div {
  box-sizing: border-box;
}
</style>