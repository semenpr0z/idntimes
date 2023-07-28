<script>
export default {
    data() {
        return {
            newsArray: [
                '2 Pilot Yunani Tewas saat Padamkan Kebakaran Hutan',
                'Ultah ke-21 Tahun, Fanbase Oniel JKT48 Hadirkan Food Truck ala Korea',
                'Raffi Ahmad dan Nagita Ingin Namai Calon Anak Ketiga dengan Inisial N',
                'Buruan Borong! Banyak Diskon Produk UMKM di Sarinah',
                'Terima Chief Executive Hong Kong, Jokowi Titip Kesejahteraan PMI',
                '7 Potret Natasha Rizky Latihan Tenis, Busana Syari Banjir Pujian',
                "McDonald's di AS Didenda Ketahuan Pekerjakan Anak di Bawah Umur",
                'Puan: Saya Serius Loh Cak Imin Masuk Bursa Cawapres Ganjar',
                'IHSG Ambruk, Ini 5 Saham Paling Cuan Seharian',
                '4 Alasan Wajah Jaemin NCT Dinilai Unik oleh Ahli Bedah Plastik'
            ]
        }
    }
}
</script>

<template>
    <section class="news">
        <h3 class="news__title">
            <svg class="news__title-left" width="17" height="4" viewBox="0 0 17 4" fill="none"
                xmlns="http://www.w3.org/2000/svg">
                <rect width="1600" height="3.92" transform="matrix(1 0 -0.642788 0.766044 -1583.9 0.919983)"
                    fill="#333333" />
            </svg>
            BERITA TERPOPULER
            <svg class="news__title-right" width="17" height="4" viewBox="0 0 17 4" fill="none"
                xmlns="http://www.w3.org/2000/svg">
                <rect width="1600" height="3.92" transform="matrix(1 0 0.642788 0.766044 0.880005 0.919983)"
                    fill="#333333" />
            </svg>
        </h3>
        <ul class="news__list">
            <li class="news__list-item" v-for="(item, index) in newsArray" :key="index">
                <span class="dot"></span>
                <a class="link" href="">{{ item }}</a>
            </li>
        </ul>
    </section>
</template>

<style lang='scss' scoped>
.news {
    width: 300px;

    &__title {
        position: relative;
        font-size: 23px;
        font-weight: normal;
        font-family: "Roboto Slab", serif;
        text-align: center;
        margin-bottom: 20px;

        &-left {
            top: calc(50% - 2px);
            position: absolute;
            left: 0;
        }

        &-right {
            position: absolute;
            right: 0;
            top: calc(50% - 2px);
        }
    }

    &__list {
        list-style: none;
        padding: 0;
        margin: 0;

        &-item {
            display: flex;
            align-items: flex-start;
            gap: 17px;
            padding-bottom: 10px;
            margin-bottom: 5px;
            border-bottom: 1px solid #d3d3d3;
            &:last-child{
                border-bottom: none;
            }


            .dot {
                display: block;
                min-width: 8px;
                min-height: 8px;
                border-radius: 50%;
                margin-top: 5px;
                background-color: #ff0000;
            }

            .link {
                text-decoration: none;
                color: #333;
            }
        }
    }
}
</style>