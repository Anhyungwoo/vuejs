<template>
  <h1>Hello, {{ title }}</h1>
  <div v-html="htmlString"></div>
  <input type="text" v-model="valueModel" />
  <br />
  <br />
  <textarea v-model="message"></textarea>
  <br />
  <select v-model="city">
    <option value="02">서울</option>
    <option value="21">붓싼</option>
    <option value="064">제주</option>
  </select>
  <br />
  <label><input type="checkbox" v-model="checked" />{{ checked }}</label>
  <br />
  <div>
    <label
      ><input type="radio" v-bind:value="radioValue1" v-model="picked" />
      서울</label
    >
    <label
      ><input type="radio" v-bind:value="radioValue2" v-model="picked" />
      부산</label
    >
    <label
      ><input type="radio" v-bind:value="radioValue3" v-model="picked" />
      제주</label
    >
    <br />
    <span>선택한 지역: {{ picked }}</span>
  </div>
  <div>
    <input type="text" v-model="textValue" />
    <button
      type="button"
      v-bind:disabled="textValue == ''"
      @click="showMessage"
    >
      Click!
    </button>
  </div>
  <br />
  <div
    class="container"
    v-bind:class="{ active: isActive, 'text-red': hasError }"
  >
    Class binding
  </div>
  <br />
  <div v-bind:style="styleObject">인라인 스타일 바인딩</div>
  <br />
  <div>
    <table>
      <thead>
        <tr>
          <th>제품명</th>
          <th>가격</th>
          <th>카테고리</th>
          <th>배송료</th>
        </tr>
      </thead>
      <tbody>
        <tr :key="i" v-for="(product, i) in productList">
          <td>{{ product.product_name }}</td>
          <td>{{ product.price }}</td>
          <td>{{ product.category }}</td>
          <td>{{ product.delivery_price }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: "world",
      htmlString: '<p style="color:red">HTML으로 작성한 문장</p>',
      valueModel: "South Korea",
      message: "텍스트에어리어",
      city: "21",
      checked: true,
      picked: "",
      radioValue1: "서울",
      radioValue2: "부산",
      radioValue3: "제주",
      textValue: "",
      isActive: true,
      hasError: false,
      styleObject: {
        color: "red",
        fontSize: "30px",
        productList: [
          {
            product_name: "기계식키보드",
            price: 25000,
            category: "노트북/태블릿",
            delivery_price: 5000,
          },
          {
            product_name: "무선마우스",
            price: 12000,
            category: "노트북/태블릿",
            delivery_price: 5000,
          },
          {
            product_name: "아이패드",
            price: 725000,
            category: "노트북/태블릿",
            delivery_price: 5000,
          },
          {
            product_name: "태블릿거치대",
            price: 32000,
            category: "노트북/태블릿",
            delivery_price: 5000,
          },
          {
            product_name: "무선충전기",
            price: 42000,
            category: "노트북/태블릿",
            delivery_price: 5000,
          },
        ],
      },
    };
  },
  methods: {
    showMessage() {
      alert(this.textValue);
    },
  },
};
</script>

<style scoped>
.container {
  width: 100%;
  height: 200px;
}

.active {
  background-color: yellow;
  font-weight: bold;
}

.text-red {
  color: red;
}

table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td,
th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}
</style>
