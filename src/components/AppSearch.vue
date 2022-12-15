<script>
import { store } from '../store.js';

export default {
    name: "AppSearch",
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="select-container">
            <label for="status">Select status:</label>
            <select name="status" id="status" v-model="store.searchStatus" @click.prevent="$emit('search')">
                <option value="chooseStatus">Choose Status</option>
                <option value="alive">Alive</option>
                <option value="dead">Dead</option>
                <option value="unknown">Unknown</option>
            </select>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables.scss' as *;
@use '../style/general.scss' as *;

.container {
    .select-container {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 20px;
        padding: 10px;

        label {
            font-size: 20px;
        }

        #status {
            padding: 10px 15px;
            background-color: $bg;
            border: 1px solid black;
        }
    }
}
</style>