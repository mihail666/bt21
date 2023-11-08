<template>
  <div class="center">
    <h3>Form bt21 <span>vue3 html css</span></h3>
    <button @click="isShow = true, arr=[]" style="width: 90px">start</button>
    <div id="result" v-if="arr.length">
        <div v-for="a in arr" :key="a">
            <li>
                login: {{ a.login }}
            </li>
            <li>
                email: {{ a.email }}
            </li>
            <li>
                name: {{ a.name }}
            </li>
            <li>
                surname: {{ a.surname}}
            </li>
            <li>
                password: {{ a.psw }}
            </li>    
        </div>
    </div>
  </div>
  <div v-show="isShow" class="modal">
    <form @submit.prevent="send" class="modal-content animate">
      <div class="imgcontainer">
        <span @click="isShow = false" class="close" title="close Modal">&times;</span>
        <img
          src="https://www.fototv.de/dateien/styles/thumbnail/public/profiles/FTV_default_avatar.png?itok=ld4eHA35"
          alt="avatar"
          class="avatar"
        />
      </div>

      <ul class="container">
        <li class="input-group">
          <label for="login"><b>login</b></label>
          <input type="text" placeholder="write your login" name="login" required v-model="login" />
        </li>
        <li class="input-group">
          <label for="email"><b>email</b></label>
          <input type="text" placeholder="email" name="email" required v-model="email" />
        </li>
        <li class="input-group">
          <label for="name"><b>name</b></label>
          <input type="text" placeholder="write your name" name="name" required v-model="name" />
        </li>
        <li class="input-group">
          <label for="surname"><b>surname</b></label>
          <input
            type="text"
            placeholder="write your name"
            name="surname"
            required
            v-model="surname"
          />
        </li>
        <li class="input-group">
          <label for="psw"><b>password</b></label>
          <input
            type="password"
            placeholder=" write your password"
            name="psw"
            required
            v-model="psw"
          />
        </li>
        <button type="submit">Send</button>
      </ul>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShow: false,
      login: '',
      email: '',
      name: '',
      surname: '',
      psw: '',
      arr: []
    }
  },

  methods: {
    send() {
      const formdata = {
        login: this.login,
        email: this.email,
        name: this.name,
        surname: this.surname,
        pse: this.psw
      }
      this.arr.push(formdata)
      this.isShow = false
      this.login = '', 
      this.email = '',
      this.name = '',
      this.surname = '',
      this.psw = ''
    }
  }
}
</script>
