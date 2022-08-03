<template>
  <div>
    <h1>This is main page</h1>
    <Counter/>
    <div>
        x:{{x}}
        y:{{y}}
    </div>
    <br>
    <div>
        <ul>
            <li v-for="user in users" :key="user.id">{{user.name}}</li>
        </ul>
    </div>
    <br>
    <div>
        <ul>
            <li v-for="user in users2" :key="user.id">{{user.name}}</li>
        </ul>
    </div>

    <br>
    <div>
        {{user.name}}
    </div>

  </div>
</template>

<script setup>
    const {x,y} = useMouse()
    const users = ref([])

    onMounted(() =>{
        fetch('https://jsonplaceholder.typicode.com/users')
        .then(response => response.json())
        .then(data => users.value = data)
    })

    const { data: users2 } = await useAsyncData('users2', () => $fetch('https://jsonplaceholder.typicode.com/users'))

    const { data: user} = await useFetch('https://jsonplaceholder.typicode.com/users/2', {pick:['id','name','email']});
</script>
