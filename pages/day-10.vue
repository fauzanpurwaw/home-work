<template>
    <div class="container">
        <div class="content w-full h-full mx-auto">
            <div class="content">
                <h1 class="title">Tugas <span class="pt text-blue-300">Day-10</span></h1>
                <div class="deskripsi">
                    <p>Disini adalah tugas <span class="pt text-slate-300">Membuat Function</span></p>
                </div>
                <div class="card-section">
                    <div class="card">
                        <div class="gambar w-full h-auto max-w-full">
                            <img src="" alt="">
                        </div>
                        <h2 class="text-lg">No 1</h2>
                        <p>sort array
                        </p>
                        <p class="mt-5" v-for="item in inputArray">
                            {{ "Name: " + item.name }} - {{ "Age : " + item.age }}
                        </p>
                        <button class="py-3 px-1 text-green-300 hover:text-emerald-600 float-right"
                            @click="sortByNameAscending">Sort it!</button>
                    </div>
                    <div class="card">
                        <div class="gambar w-full h-auto max-w-full">
                            <img src="" alt="">
                        </div>
                        <h2 class="text-lg">No 2</h2>
                        <p>Insert Text :
                        </p>
                        <input class="w-full p-2 mt-5 text-emerald-950" type="text" id="no1" v-model="txtNo1">
                        <!-- <button class="py-3 px-1 text-green-300 hover:text-emerald-600" >click</button> -->
                        <p class="mt-5 h-48 overflow-auto">{{ convertText }}</p>
                    </div>
                    <div class="card">
                        <div class="gambar w-full h-auto max-w-full">
                            <img src="" alt="">
                        </div>
                        <h2 class="text-lg">No 3</h2>
                        <p>
                            Insert number
                        </p>
                        <div class="p-1 h-10 overflow-y-auto">
                            <span v-for="item in number">
                                {{ item + " " }}
                            </span>
                        </div>
                        <div class="grid grid-cols-3 w w-full h-fit mt-5 mb-5">
                            <button class="border border-green-400 hover:text-green-400" @click="plusnumber(1)">1</button>
                            <button class="border border-green-400 hover:text-green-400" @click="plusnumber(2)">2</button>
                            <button class="border border-green-400 hover:text-green-400" @click="plusnumber(3)">3</button>
                            <button class="border border-green-400 hover:text-green-400" @click="plusnumber(4)">4</button>
                            <button class="border border-green-400 hover:text-green-400" @click="plusnumber(5)">5</button>
                            <button class="border border-green-400 hover:text-green-400" @click="plusnumber(6)">6</button>
                            <button class="border border-green-400 hover:text-green-400" @click="plusnumber(7)">7</button>
                            <button class="border border-green-400 hover:text-green-400" @click="plusnumber(8)">8</button>
                            <button class="border border-green-400 hover:text-green-400" @click="plusnumber(9)">9</button>
                        </div>
                        <button class="py-3 px-1 text-green-300 hover:text-emerald-600" @click="change">cek</button>
                        <button class="py-3 px-1 text-green-300 hover:text-emerald-600 float-right"
                            @click="clear">clear</button>
                        <div class="overflow-y-auto h-20">
                            <span v-for="item in numberChanged">
                                {{ item + " " }}
                            </span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
body {
    @apply bg-gradient-to-r from-slate-900 from-20% via-slate-800 via-50% to-emerald-950 to-90% font-mono;
}

.container {
    height: 100vh;
    @apply mx-auto;
}

.content {
    @apply flex flex-col justify-center w-full p-5;
}

.header {
    @apply w-80;
}

.title {
    text-shadow: -2px 5px 10px rgb(0, 134, 45);
    @apply text-5xl font-bold text-emerald-500;
}

.pt {
    text-shadow: -2px 2px 10px rgb(1, 112, 177);
}

.deskripsi {
    @apply p-3 text-slate-500 mt-5;
}

.card-section {
    @apply flex flex-wrap gap-5 sm:justify-normal justify-center w-full mt-28;
}

.card {
    @apply mx-auto p-6 border border-green-500 rounded-lg bg-gray-800 text-slate-400 max-w-fit w-72 h-96 shadow-lg shadow-emerald-800;
    min-width: 18rem;
}
</style>

<script>
export default {
    data() {
        return {
            txtNo1: "",
            convertedText: "your text here",
            number: [],
            numberChanged: [],
            inputArray: [
                { name: "John", age: 25 },
                { name: "Jane", age: 30 },
                { name: "John", age: 35 },
                { name: "Alice", age: 28 }
            ],
        }
    },
    methods: {
        // convertText() {
        //     if (this.txtNo1 === "") {
        //         this.convertedText = "Insert Text";
        //     } else {
        //         let words = this.txtNo1.split(' ');
        //         let char = [];
        //         for (let i = 0; i < words.length; i++) {
        //             char[i] = words[i].split('').join("@");
        //         }
        //         this.convertedText = char.join(" ");
        //     }
        // },
        change() {
            this.numberChanged = [];
            let hasil = 0;
            for (let i = 0; i < this.number.length; i++) {
                hasil += this.number[i];
                this.numberChanged.push(hasil)
            }
        },
        plusnumber(n) {
            this.number.push(n);
        },
        clear() {
            this.number = [];
        },
        sortByNameAscending() {
            this.inputArray = this.inputArray.sort(function (a, b) {
                if (a.name < b.name) {
                    return -1;
                }
                if (a.name > b.name) {
                    return 1;
                }
                return 0;
            });
        }
    },
    computed: {
        convertText() {
            let words = this.txtNo1.split(' ');
            let char = [];
            for (let i = 0; i < words.length; i++) {
                char[i] = words[i].split('').join("@");
            }
            return char.join(" ");
        }
    }
}
</script>