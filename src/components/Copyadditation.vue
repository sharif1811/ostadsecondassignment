<script setup>
import { ref } from 'vue';

const popup = ref(false);
const editpopup = ref(false);
const tasks = ref([]); // Array to store tasks

function edit() {
  // Implement your edit logic here
}

function submitTask(taskName, taskTime) {
  tasks.value.push({ name: taskName, time: taskTime });

  popup.value = false; // Close the popup after submitting
}

</script>

<template>
    <div>
        <div class="card">
            <div class="card-body">
                <table class="table table-bordered">
                    <tr>
                        <th>Name</th>
                        <th>Time</th>
                        <th>Action</th>
                    </tr>
                    <tr v-for="(task, index) in tasks" :key="index">
                        <td>{{ task.name }}</td>
                        <td>{{ task.time }}</td>
                        <td><a href="" class="btn bg-success text-white" @click.prevent="popup=true">Edit</a></td>
                    </tr>
                </table>
            </div>
        </div>
    </div>
    <button class="btn btn-primary mt-5" @click="popup = true">Show Popup</button>
    <div class="mt-5 d-flex" >
        <div class="card" v-show="popup">
            <form @submit.prevent="submit">
                <button @click="popup = false" class="btn btn-danger mb-2">Close</button>
                <input v-model="taskName" required type="text" name="" placeholder="Enter Task Name" class="form-control py-2 px-4"><br>
                <input v-model="taskTime" required type="number" name="" placeholder="Enter Number" class="form-control py-2 px-4"><br>
                <button type="submit" @click="submitTask(taskName,taskTime)" class="btn btn-success">Submit</button>
            </form>
        </div>
    </div>
</template>


