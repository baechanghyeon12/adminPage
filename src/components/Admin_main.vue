<template>
  <div>
    <div
      v-if="$store.state.listNumber == 0"
      style="
        display: flex;
        align-items: center;
        flex-direction: column;
      "
    >
    <h4 style="margin: 10px 0;">개인유저 리스트</h4>
      <table>
        <thead>
          <tr>
            <th></th>
            <th>번호</th>
            <th>이름</th>
            <th>이메일</th>
            <th>휴대폰 번호</th>
            <th>비밀번호 질문</th>
            <th>비밀번호 답변</th>
            <th>주소</th>
            <th>아이디</th>
            <th>권한</th>
            <th>가입 날짜</th>
            <th>
              <button
                @click="$store.dispatch('deleteUser')"
                style="color: black"
              >
                탈퇴
              </button>
            </th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="data in $store.state.userList['indi']" :key="data">
            <td>
              <input
                @change="$store.commit('userIdList', data.id)"
                type="checkbox"
                class="indiuser"
              />
            </td>
            <td>{{ data.id }}</td>
            <td>{{ data.name }}</td>
            <td>{{ data.email }}</td>
            <td>{{ data.phone_no }}</td>
            <td>{{ data.pw_question }}</td>
            <td>{{ data.pw_answer }}</td>
            <td>{{ data.u_addr }}</td>
            <td>{{ data.u_id }}</td>
            <td>{{ data.u_at }}</td>
            <td>{{ data.created_at }}</td>
            <td></td>
          </tr>
        </tbody>
      </table>
      <!-- <button v-for="n in $store.state.maxIndiUserPageNum" :key="n" @click="$store.dispatch('getUserStateList', n)">{{ n }}</button> -->
      <nav aria-label="Page navigation example" style="margin-top: 15px;">
        <ul class="pagination">
          <li class="page-item">
            <a class="page-link" @click="$store.dispatch('getUserStateList')" aria-label="Previous">
              <span aria-hidden="true">&laquo;</span>
            </a>
          </li>
          <li class="page-item" v-for="n in $store.state.maxIndiUserPageNum" :key="n" @click="$store.dispatch('getUserStateList', n)"><a class="page-link" href="#">{{ n }}</a></li>
          <li class="page-item">
            <a class="page-link" @click="$store.dispatch('getUserStateList', $store.state.maxIndiUserPageNum)" aria-label="Next">
              <span aria-hidden="true">&raquo;</span>
            </a>
          </li>
        </ul>
      </nav>
    </div>
    <div v-if="$store.state.listNumber == 1" 
      style="
        display: flex;
        align-items: center;
        flex-direction: column;
      ">
    <h4 style="margin: 10px 0;">공인중개사 리스트</h4>
      <table>
        <thead>
          <tr>
            <th></th>
            <th>번호</th>
            <th>이름</th>
            <th>이메일</th>
            <th>휴대폰 번호</th>
            <th>비밀번호 질문</th>
            <th>비밀번호 답변</th>
            <th>라이센스 번호</th>
            <th>주소</th>
            <th>아이디</th>
            <th>권한</th>
            <th>가입 날짜</th>
            <th>
              <button
                @click="$store.dispatch('deleteUser')"
                style="color: black"
              >
              탈퇴
              </button>
            </th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="data in $store.state.userList['realtor']" :key="data">
            <td>
              <input
                @change="$store.commit('userIdList', data.id)"
                type="checkbox"
                class="realtor"
              />
            </td>
            <td>{{ data.id }}</td>
            <td>{{ data.name }}</td>
            <td>{{ data.email }}</td>
            <td>{{ data.phone_no }}</td>
            <td>{{ data.pw_question }}</td>
            <td>{{ data.pw_answer }}</td>
            <td>{{ data.seller_license }}</td>
            <td>{{ data.u_addr }}</td>
            <td>{{ data.u_id }}</td>
            <td>{{ data.u_at }}</td>
            <td>{{ data.created_at }}</td>
            <td></td>
          </tr>
        </tbody>
      </table>
      <!-- <button v-for="n in $store.state.maxRealtorUserPageNum" :key="n" @click="$store.dispatch('getUserStateList', n)">{{ n }}</button> -->
      <nav aria-label="Page navigation example" style="margin-top: 15px;">
        <ul class="pagination">
          <li class="page-item">
            <a class="page-link" @click="$store.dispatch('getUserStateList')" aria-label="Previous">
              <span aria-hidden="true">&laquo;</span>
            </a>
          </li>
          <li class="page-item" v-for="n in $store.state.maxIndiUserPageNum" :key="n" @click="$store.dispatch('getUserStateList', n)"><a class="page-link">{{ n }}</a></li>
          <li class="page-item">
            <a class="page-link" @click="$store.dispatch('getUserStateList', $store.state.maxIndiUserPageNum)" aria-label="Next">
              <span aria-hidden="true">&raquo;</span>
            </a>
          </li>
        </ul>
      </nav>
    </div>
    <div v-if="$store.state.listNumber == 2"
      style="
        display: flex;
        align-items: center;
        flex-direction: column;
      ">
    <h4 style="margin: 10px 0;">매물 리스트</h4>
      <table>
        <thead>
          <tr>
            <th></th>
            <th>번호</th>
            <th>이름</th>
            <th>주소</th>
            <th>매매유형</th>
            <th>가격</th>
            <th>대형동물 가능 여부</th>
            <th>평수</th>
            <th>층수</th>
            <th>가까운 역</th>
            <th>올린 유저 번호</th>
            <th>작성 날짜</th>
            <th>
              <button
                @click="$store.dispatch('deleteStateList')"
                style="color: black"
              >
              탈퇴
              </button>
            </th>
          </tr>
        </thead>
        <tbody>
          
          <tr v-for="data in $store.state.stateList" :key="data">
            <td>
              <input
              @change="$store.commit('stateNumber', data.s_no)"
              type="checkbox"
              class="state"
              />
            </td>
            <td>{{ data.s_no }}</td>
            <td><strong><a :href="'http://192.168.0.129/sDetail/' + data.s_no" target="_blank">{{ data.s_name }}</a></strong></td>
            <td>{{ data.s_add }}</td>
            <td>{{ data.s_type }}</td>
            <td>{{ data.p_deposit }}</td>
            <td>{{ data.animal_size }}</td>
            <td>{{ data.s_size }}</td>
            <td>{{ data.s_fl }}</td>
            <td>{{ data.s_stai }}</td>
            <td>{{ data.u_no }}</td>
            <td>{{ data.created_at }}</td>
            <td></td>
          </tr>
        </tbody>
      </table>
      <a-table :row-selection="rowSelection" :columns="columns" :data-source="data" />
      <!-- <button v-for="n in $store.state.maxStatesPageNum" :key="n" @click="$store.dispatch('getUserStateList', n)">{{ n }}</button> -->
        <nav aria-label="Page navigation example" style="margin-top: 15px;">
          <ul class="pagination">
            <li class="page-item">
              <a class="page-link" @click="$store.dispatch('getUserStateList')" aria-label="Previous">
                <span aria-hidden="true">&laquo;</span>
              </a>
            </li>
            <li class="page-item" v-for="n in $store.state.maxStatesPageNum" :key="n" @click="$store.dispatch('getUserStateList', n)"><a class="page-link" href="#">{{ n }}</a></li>
            <li class="page-item">
              <a class="page-link" @click="$store.dispatch('getUserStateList', $store.state.maxStatesPageNum)" aria-label="Next">
                <span aria-hidden="true">&raquo;</span>
              </a>
            </li>
          </ul>
        </nav>
    </div>
  </div>
</template>
<!-- <script>
import { computed, ref, unref } from 'vue';
import { Table } from 'ant-design-vue';
const columns = [{
  title: 'Name',
  dataIndex: 'name',
}, {
  title: 'Age',
  dataIndex: 'age',
}, {
  title: 'Address',
  dataIndex: 'address',
}];
const data = [];
for (let i = 0; i < 46; i++) {
  data.push({
    key: i,
    name: `Edward King ${i}`,
    age: 32,
    address: `London, Park Lane no. ${i}`,
  });
}
const selectedRowKeys = ref([]); // Check here to configure the default column

const onSelectChange = changableRowKeys => {
  console.log('selectedRowKeys changed: ', changableRowKeys);
  selectedRowKeys.value = changableRowKeys;
};
const rowSelection = computed(() => {
  return {
    selectedRowKeys: unref(selectedRowKeys),
    onChange: onSelectChange,
    hideDefaultSelections: true,
    selections: [Table.SELECTION_ALL, Table.SELECTION_INVERT, Table.SELECTION_NONE, {
      key: 'odd',
      text: 'Select Odd Row',
      onSelect: changableRowKeys => {
        let newSelectedRowKeys = [];
        newSelectedRowKeys = changableRowKeys.filter((_key, index) => {
          if (index % 2 !== 0) {
            return false;
          }
          return true;
        });
        selectedRowKeys.value = newSelectedRowKeys;
      },
    }, {
      key: 'even',
      text: 'Select Even Row',
      onSelect: changableRowKeys => {
        let newSelectedRowKeys = [];
        newSelectedRowKeys = changableRowKeys.filter((_key, index) => {
          if (index % 2 !== 0) {
            return true;
          }
          return false;
        });
        selectedRowKeys.value = newSelectedRowKeys;
      },
    }],
  };
});
</script> -->
<script>

export default {
  name: "Admin_main",
};
</script>
<style></style>
