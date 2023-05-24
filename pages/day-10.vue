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
                        <p class="mt-5" v-for="item in sortedArray">
                            {{"Name: " + item.name }} - {{ "Age : " + item.age }}
                        </p>
                    </div>
                    <div class="card">
                        <div class="gambar w-full h-auto max-w-full">
                            <img src="" alt="">
                        </div>
                        <h2 class="text-lg">No 2</h2>
                        <p>Masukkan Text :
                        </p>
                        <input class="w-full p-2 mt-5 text-emerald-950" type="text" id="no1" v-model="txtNo1">
                        <button class="py-3 px-1 text-green-300 hover:text-emerald-600" @click="convertText">click</button>
                        <p class="mt-5">{{ convertedText }}</p>
                    </div>
                    <div class="card">
                        <div class="gambar w-full h-auto max-w-full">
                            <img src="" alt="">
                        </div>
                        <h2 class="text-lg">No 3</h2>
                        <p>
                            Masukkan Angka
                        </p>
                        <span v-for="item in angka">
                            {{ item + " " }}
                        </span>
                        <div class="grid grid-cols-3 w w-full h-fit mt-5 mb-5">
                            <button class="border border-green-400 hover:text-green-400" @click="tambahAngka(1)">1</button>
                            <button class="border border-green-400 hover:text-green-400" @click="tambahAngka(2)">2</button>
                            <button class="border border-green-400 hover:text-green-400" @click="tambahAngka(3)">3</button>
                            <button class="border border-green-400 hover:text-green-400" @click="tambahAngka(4)">4</button>
                            <button class="border border-green-400 hover:text-green-400" @click="tambahAngka(5)">5</button>
                            <button class="border border-green-400 hover:text-green-400" @click="tambahAngka(6)">6</button>
                            <button class="border border-green-400 hover:text-green-400" @click="tambahAngka(7)">7</button>
                            <button class="border border-green-400 hover:text-green-400" @click="tambahAngka(8)">8</button>
                            <button class="border border-green-400 hover:text-green-400" @click="tambahAngka(9)">9</button>
                        </div>
                        <button class="py-3 px-1 text-green-300 hover:text-emerald-600" @click="ubahAngka">cek</button>
                        <button class="py-3 px-1 text-green-300 hover:text-emerald-600 float-right"
                            @click="clear">clear</button>
                        <p>
                            <span v-for="item in angkaTerubah">
                                {{ item + " " }}
                            </span>
                        </p>
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
</style>

<script>
export default {
    data() {
        return {
            txtNo1: "",
            convertedText: "text mu disini",
            angka: [],
            angkaTerubah: [],
            inputArray: [
                { name: "John", age: 25 },
                { name: "Jane", age: 30 },
                { name: "John", age: 35 },
                { name: "Alice", age: 28 }
            ],
            sortedArray: [],
        }
    },
    methods: {
        convertText() {
            if (this.txtNo1 === "") {
                this.convertedText = "Masukkan Text";
            } else {
                let words = this.txtNo1.split(' ');
                let char = [];
                for (let i = 0; i < words.length; i++) {
                    char[i] = words[i].split('').join("@");
                }
                this.convertedText = char.join(" ");
            }
        },
        ubahAngka() {
            this.angkaTerubah = [];
            let hasil = 0;
            for (let i = 0; i < this.angka.length; i++) {
                hasil += this.angka[i];
                this.angkaTerubah.push(hasil)
            }
        },
        tambahAngka(n) {
            this.angka.push(n);
        },
        clear() {
            this.angka = [];
        },
        sortByNameAscending(sortList) {
            this.sortedArray = sortList.sort(function (a, b) {
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
    mounted() {
        this.sortByNameAscending(this.inputArray);
    }
}
</script>