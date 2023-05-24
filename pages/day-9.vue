<template>
    <div class="container">
        <div class="content w-full h-full mx-auto">
            <div class="content">
                <h1 class="title">Tugas <span class="pt text-blue-300">Day-9</span></h1>
                <div class="deskripsi">
                    <p>Disini adalah tugas <span class="pt text-slate-300">Menampilkan Data JSON dalam UI</span></p>
                </div>
                <div class="card-section" v-html="htmlString">
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
            htmlString: "",
            products: [
                {
                    name: "Action Figure Hutao",
                    description: "ini action figure hutao",
                    qty: 5,
                    price: 1000000,
                    discount: 5,//percent
                    // image: "/img/hutao.jpg",
                    detail: {
                        comments: {
                            name: "@rizzz_",
                            comment: "barang bagus",
                            date: "12-02-2023"
                        },
                        rating: 8.32,
                        sold: 2
                    }
                },
                {
                    name: "Action Figure Ganyu",
                    description: "ini action figure Ganyu",
                    qty: 7,
                    price: 1200000,
                    discount: 5,//percent
                    // image: "/img/Ganyu.jpg",
                    detail: {
                        comments: {
                            name: "@jaanck_",
                            comment: "barang bagus",
                            date: "11-02-2023"
                        },
                        rating: 8.12,
                        sold: 1
                    }
                },
                {
                    name: "Action Figure Shenhe",
                    description: "ini action figure Shenhe",
                    qty: 2,
                    price: 1500000,
                    discount: 5,//percent
                    // image: "/img/Shenhe.jpg",
                    detail: {
                        comments: {
                            name: "@ramli_",
                            comment: "barang Mantap",
                            date: "15-02-2023"
                        },
                        rating: 8.22,
                        sold: 0
                    }
                },
            ],
        }
    },
    mounted() {
        console.log(this.products.length)

        for (let a of this.products) {
            this.htmlString += "<div class='card'>";
            this.htmlString += "<ol class='mt-3'>";
            this.htmlString += `<li>Name : ${a.name}</li>`;
            this.htmlString += `<li>Description : ${a.description}</li>`;
            this.htmlString += `<li class='mt-5'>Qty : ${a.qty}</li>`;
            this.htmlString += `<li>Price : ${a.price}</li>`;
            this.htmlString += `<li>Discount : ${a.discount}</li>`;
            this.htmlString += `<li>Rating : ${a.detail.rating}</li>`;
            this.htmlString += `<li>Sold : ${a.detail.sold}</li>`;
            this.htmlString += "<li>";
            this.htmlString += "<ol class='text-right mt-8'>";
            this.htmlString += `<li>Commentator : ${a.detail.comments.name}</li>`;
            this.htmlString += `<li>Comment : ${a.detail.comments.comment}</li>`;
            this.htmlString += `<li>Date : ${a.detail.comments.date}</li>`;
            this.htmlString += "</ol>";
            this.htmlString += "</li>";
            this.htmlString += "</ol>";
            this.htmlString += "</div>";
        }
    }
}

</script>
