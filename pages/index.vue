<template>
  <div class="container">
    <div class="content w-full h-full mx-auto">
      <div class="content">
        <h1 class="title">Home Work at <span class="pt text-blue-300">JUKe Soulutions</span></h1>
        <div class="deskripsi">
          <p>Disini Tempat Tugas-tugas Harian saya saat Program BootCamp Front-End Developer di PT.JUKe Solutions.</p>
        </div>
        <div class="card-section">
          <NuxtLink to="day-8">
            <div class="card">
              <div class="gambar w-full h-auto max-w-full">
                <img src="" alt="">
              </div>
              <h2 class="text-lg">Day-8</h2>
              <p>Membuat diskon pembelian (JS)</p>
            </div>
          </NuxtLink>
          <div class="card">
            <div class="gambar w-full h-auto max-w-full">
              <img src="" alt="">
            </div>
            <h2 class="text-lg">Day-8</h2>
            <p>Membuat diskon pembelian (JS)</p>
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
  @apply mx-auto ;
}

.content {
  @apply flex flex-col justify-center w-full p-5;
}

.title {
  text-shadow: -2px 5px 10px rgb(0, 134, 45);
  @apply text-5xl font-bold text-emerald-500;
}

.pt {
  text-shadow: -2px 2px 10px rgb(1, 112, 177);
}

.deskripsi {
  @apply p-3 text-slate-500;
}

.card-section {
  @apply flex flex-wrap gap-5 sm:justify-normal justify-center w-full mt-28;
}

.card {
  @apply p-6 border border-green-500 rounded-lg bg-gray-800 text-slate-400 hover:bg-gray-900 hover:text-slate-300 max-w-fit w-72 h-96 shadow-lg shadow-emerald-800  hover:shadow-gray-900;
  min-width: 18rem;
}</style>