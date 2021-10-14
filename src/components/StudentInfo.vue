<template>
    <div>
        <div class="container">
            <div>
                <div class="left">
                    <div>
                        <span>Full name: </span>
                        <span>{{ info.name }}</span>
                    </div>
                    <div>
                        <span>Gender: </span>
                        <span>{{ info.gender }}</span>
                    </div>
                    <div>
                        <span>Email: </span>
                        <span>{{ info.email }}</span>
                    </div>
                </div>
                <div class="right">
                    <div>
                        <span>StudentID: </span>
                        <span>{{ info.id }}</span>
                    </div>
                    <div>
                        <span>Location: </span>
                        <span>{{ info.location }}</span>
                    </div>
                    <div>
                        <span>Phone: </span>
                        <span>{{ info.phone }}</span>
                    </div>
                </div>
            </div>
            <div>
                <button @click.prevent="deleteInfo(index)">Delete</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['info', 'deleteInfo', 'index'],
    methods: {
        
    }
}
</script>

<style scoped>
.container > div {
    display: flex;
}
input {
    border-radius: 3px;
    outline: none;
    border: none;
}
button {
    cursor: pointer;
}
.container {
    margin-top: 5px;
    background-color: #EDC856;
    width: 550px;
    padding: 10px 10px;
    border-radius: 5px;
    font-family: Arial, Helvetica, sans-serif;
}
.left {
    margin-right: 10px;
}
.left > div,
.right > div {
    margin-bottom: 5px;
}
</style>