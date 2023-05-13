<template>
    <h1>Index</h1>
    <div class="d-flex justify-content-center fs-1 mb-3">
        <div class="spinner-grow text-danger" style="width: 6rem; height: 6rem;" role="status">
            <span class="visually-hidden">Loading...</span>
        </div>
    </div>
    <div class="mt-5 px-5 d-flex justify-content-center">
        <div class="mb-3">
            <label for="exampleInputEmail1 fs-5" class="form-label bg-primary">Test LocalForage</label>
            <input v-model="inputLocal" type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
            <div id="emailHelp" class="form-text">Enter some text and refresh the page to test localstorage</div>
        </div>

        <button @click="changeLocal()" class="btn btn-primary">Guardar</button>
    </div>
    
    <div class="float-end text-muted fs-3">
        {{menuStore.someState}}

    </div>
</template>
<script setup>
import { useStore } from '~/store/states';

const menuStore = useStore();
const inputLocal = ref('');
const changeLocal = ()=>{
    menuStore.someState=inputLocal.value;
}
</script>