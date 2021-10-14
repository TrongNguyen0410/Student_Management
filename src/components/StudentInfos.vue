<template>
    <div>
        <div class="container">
            <div>
                <div class="left">
                    <div>
                        <span>Full name: </span>
                        <input type="text" v-model="newName">
                    </div>
                    <div>
                        <span>Gender: </span>
                        <input type="radio" name="gender" @click="newGender = 'Male'">&nbsp;
                        <span>Male</span>
                        <input type="radio" name="gender" @click="newGender = 'Female'">&nbsp;
                        <span>Female</span>
                    </div>
                    <div>
                        <span>Email: </span>
                        <input type="email" v-model="newEmail">
                    </div>
                </div>
                <div class="right">
                    <div>
                        <span>StudentID: </span>
                        <input type="text" v-model="newID">
                    </div>
                    <div>
                        <span>Location: </span>
                        <input type="text" v-model="newLocation">
                    </div>
                    <div>
                        <span>Phone: </span>
                        <input type="text" v-model="newPhone">
                    </div>
                </div>
            </div>
            <div>
                <button @click="AddInfo()">Add</button>
            </div>
        </div>
        <StudentInfo 
            v-for="(info, index) in infos" :key="index"
            :info="info"
            :index='index'
            :deleteInfo='deleteInfo'

        />
    </div>
</template>

<script>
import StudentInfo from './StudentInfo'
export default {
    components:{StudentInfo},
    data(){
        return {
            newName: '',
            newGender: '',
            newEmail: '',
            newID: '',
            newLocation: '',
            newPhone: '',
            infos: []
        }
    },
    methods: {
        AddInfo(){
            this.infos.push({
                name: this.newName,
                gender: this.newGender,
                email: this.newEmail,
                id: this.newID,
                location: this.newLocation,
                phone: this.newPhone
                });
            this.newName = '';
            this.newGender = '';
            this.newEmail = '';
            this.newID = '';
            this.newLocation = '';
            this.newPhone = '';
        },
        deleteInfo(index){
            this.infos.splice(index, 1);
        }
        
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
    background-color: #7A75D1;
    width: 550px;
    padding: 10px 10px;
    border-radius: 5px;
    font-family: Arial, Helvetica, sans-serif;
    color: white;
}
.left {
    margin-right: 10px;
}
.left > div,
.right > div {
    margin-bottom: 5px;
}
</style>