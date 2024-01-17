<script setup>
    import {ref} from 'vue';
    const popup = ref(false);

    function edit(){

    }
    function submit(){

    }

</script>
<template> 
    <div>
        <div class="card">
            <div class="card-body">
                <table class="table table-borderd">
                    <tr>
                        <th>Name</th>
                        <th>Time</th>
                        <th>Action</th>
                    </tr>
                    <tr>
                        <td>Task-1</td>
                        <td>20min</td>
                        <td><a href="" class="btn bg-success text-white" >Edit</a></td>
                    </tr>
                </table>
            </div>
        </div>
    </div>
    <button class="btn btn-primary mt-5" @click="popup=true">Show Popup</button>
        <div class="mt-5" v-show="popup">
            <div class="card">
                <form action="">
                    <button @click="popup=false" class="btn btn-danger mb-2">Close</button>
                    <input type="text" name="" placeholder="Enter Task Name" class="form-control py-2 px-4"><br>
                    <input type="number" name="" placeholder="Enter Number" class="form-control py-2 px-4"><br>
                    <button class="btn btn-success">Submit</button>
                </form>  
            </div>
        </div>
</template>
<style scoped>

</style>