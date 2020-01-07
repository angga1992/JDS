<template>
  <div class="container bg-gray-600">
    <div class="flex flex-col h-full min-h-screen w-full px-4">
        <div class="flex justify-center items-center h-40">
            <span class="text-xl font-bold  text-white">Formulir Pendaftaran Online</span>
        </div>
      <div class="mb-4 mt-15 text-left items-start justify-start">
        <label class="block text-gray-200 text-sm font-bold mb-2"
               for="name">
          Nama Lengkap
        </label>
        <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
               id="name"
               type="text"
               v-model="payload['name']"
               placeholder="Nama Lengkap">
      </div>

      <div class="mb-4 text-left items-start justify-start">
        <label class="block text-gray-200 text-sm font-bold mb-2"
               for="date">
          Tanggal Lahir
        </label>
        <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
               id="date"
               type="date"
               v-model="payload['date']"
               placeholder="Tanggal Lahir">
      </div>

      <div class="mb-4 text-left items-start justify-start">
        <label class="block text-gray-200 text-sm font-bold mb-2"
               for="username">
          Jenis Kelamin
        </label>
        <input type="radio" v-model="payload['gender']" class="form-radio" name="accountType" value="pria">
        <span class="ml-2 mr-4 text-white">Pria</span>

        <input type="radio" v-model="payload['gender']" class="form-radio " name="accountType" value="wanita">
        <span class="ml-2 text-white">Wanita</span>

      </div>

      <div class="mb-4 text-left items-start justify-start">
        <label class="block text-gray-200 text-sm font-bold mb-2"
               for="name">
          Alamat
        </label>
        <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
               id="address"
               type="text"
               v-model="payload['address']"
               placeholder="Alamat">
      </div>

      <div class="mb-20 text-left items-start justify-start">
        <label class="block text-gray-200 text-sm font-bold mb-2"
               for="name">
          Daftar Riwayat Pekerjaan
        </label>
        <div v-for="(i, index) in count" :key="index">
            <input class="shadow appearance-none border rounded w-full my-1 py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
               :id="`name${i}`"
               type="text"
               :placeholder="`Riwayat Pekerjaan ${i}`">
        </div>
        <div class="flex text-center justify-center mt-2">
            <button v-on:click.prevent="increment" class="bg-yellow-500 rounded-lg py-1 px-3 text-white focus:outline-none cursor-pointer">
                Tambah Riwayat Pekerjaan
            </button>
        </div>
      </div>

      <div class="bottom-0 sticky">
          <button 
            :class="[payload['name'] && payload['date'] && payload['gender'] && payload['address'] ? 'bg-green-600' : 'bg-gray-500']"
            class="cursor-pointer flex w-full rounded text-white py-2 px-4 text-center item-center justify-center focus:outline-none">
              <span>
                  Simpan
              </span>
          </button>
      </div>

    </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            payload: {
                name: '',
                date: '',
                gender: '',
                address: ''
            },
            count: 2
        }
    },
    methods: {
        increment () {
            this.count++;
        },
    }
}
</script>