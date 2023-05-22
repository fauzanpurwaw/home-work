<template>
    <div class="container">
        <div class="content w-full h-full mx-auto">
            <div class="content-day-8">
                <div class="header">
                    <h1 class="title">Tugas <span class="pt text-blue-300">Day-8</span></h1>
                    <div class="deskripsi">
                        <p>Disini adalah tugas <span class="pt text-slate-300">Membuat diskon pembelian (JS)</span></p>
                    </div>
                </div>
                <div class="card-day-8">
                    <h1 class="text-lg pt text-white">Masukkan Harga</h1>
                    <div class="flex gap-3 mt-5 w-full">
                        <input type="number" class="inHarga">
                        <button class="text-green-500 hover:text-emerald-600" @click="cekDiskon">click</button>
                    </div>
                    <table class="w-full h-fit mt-10 text-white" :class="{ hidden: total.status }">
                        <tr>
                            <td class="border-r border-green-500 px-1">SubTotal</td>
                            <td class="px-1 text-right">Rp.{{ subtotal }}</td>
                        </tr>
                        <tr>
                            <td class="border-r border-green-500 px-1">Diskon</td>
                            <td class="px-1 text-right">{{ diskon }}%</td>
                        </tr>
                        <tr>
                            <td class="border-r border-green-500 px-1">Potongan</td>
                            <td class="px-1 text-right">Rp.{{ potongan }}</td>
                        </tr>
                        <tr>
                            <td class="border-r border-green-500 px-1">Total</td>
                            <td class="px-1 text-right">Rp.{{ total }}</td>
                        </tr>
                    </table>
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
    @apply mx-auto;
}

.content-day-8 {
    height: 100vh;
    @apply flex justify-center items-center w-full p-5 gap-5;
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

.card-day-8 {
    @apply p-6 border border-green-500 rounded-lg bg-gray-800 text-slate-400 max-w-fit w-72 h-96 shadow-lg shadow-emerald-800;
    min-width: 18rem;
}
</style>

<script>
export default {
    data() {
        return {
            subtotal: 0,
            diskon: 0,
            potongan: 0,
            total: 0
        }
    },
    methods: {
        cekDiskon() {
            this.subtotal = document.querySelector(".inHarga").value;
            var hargaTotal = this.subtotal;
            if (hargaTotal >= 100000) {
                this.diskon = 10;
                this.potongan = this.diskon / 100 * hargaTotal;
                this.total = hargaTotal - this.potongan;
            } else if (hargaTotal >= 50000 && hargaTotal < 100000) {
                this.diskon = 5;
                this.potongan =this.diskon / 100 * hargaTotal;
                this.total = hargaTotal - this.potongan;
            } else if (hargaTotal > 0 && hargaTotal < 50000) {
                this.diskon = 0;
                this.potongan =this.diskon / 100 * hargaTotal;
                this.total = hargaTotal - this.potongan;
            }
        },
    },
}
</script>