<script>
import Button from './components/Button.vue';

export default {
    data() {
        return {
            pages: [
                { title: '#GenZMemilih', link: '', more: null },
                { title: 'Quiz', link: '', more: null, img: '/images/quiz.png' },
                { title: 'News', link: '', more: null },
                { title: 'Business', link: '', more: null },
                { title: 'Sport', link: '', more: null },
                { title: 'Tech', link: '', more: null },
                { title: 'Hype', link: '', more: null },
                { title: 'Korea', link: '', more: null, active: true },
                { title: 'Life', link: '', more: null },
                { title: 'Health', link: '', more: null },
                { title: 'Community', link: '', more: null },
                {
                    title: 'Regional',
                    link: '',
                    more: [
                        {
                            type: 'Regional',
                            pages: ['IDN Times', 'Jawa Barat', 'Banten', 'Jawa Tengah', 'Jogja', 'Jawa Timur', 'Bali', 'Sumatera Utara', 'Sulawesi Selatan', 'Kalimantan Timur', 'Sumatera Selatan', 'Lampung', 'NTB']
                        }
                    ]
                },
                {
                    title: 'Lainnya',
                    link: '',
                    more: [
                        {
                            type: 'Kategori',
                            pages: ['Tanya Jawab', 'Automotive', 'Science', 'Men', 'Food', 'Opinion', 'Fiction', 'Index', 'Travel']
                        },
                        {
                            type: 'Event',
                            pages: ['#COZIMMOVING', '#1000ASPIRASIINDONESIAMUDA', '#AKUPEREMPUAN', '#KITAIDN', '#ANTIPUASAKUOTA', '#LIPUTANKHUSUS']
                        }
                    ],
                    download: true
                }
            ],
            dropdownOpened: false,
            channels: [
                [
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/idn.png', link: 'https://www.idn.media/product', alt: 'idn' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/idntimes.png', link: 'https://www.idntimes.com', alt: 'idntimes' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/popbela.png', link: 'https://www.popbela.com', alt: 'popbela' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/popmama.png', link: 'https://www.popmama.com', alt: 'popmama' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/yummy.png', link: 'https://www.yummy.co.id', alt: 'yummy' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/fortune.png', link: 'https://www.fortune.com', alt: 'fortune' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/ggwp.png', link: 'https://www.ggwp.id', alt: 'ggwp' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/duniaku.png', link: 'https://duniaku.idntimes.com', alt: 'duniaku' },
                ],
                [
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/idn-creative.png', link: 'https://www.idn.media/product', alt: 'idn-creative' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/ice.png', link: 'https://www.ice.id', alt: 'ice' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/morf.png', link: 'https://www.morf.id', alt: 'morf' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/idn-event.png', link: 'https://www.idn.media/product', alt: 'idn-event' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/bluebird-idn-ooh.png', link: 'https://www.idn.media/product', alt: 'bluebird-idn-ooh' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/idn-pictures.png', link: 'https://www.idn.media/product', alt: 'idn-pictures' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/idn-foundation.png', link: 'https://www.idn.media/product', alt: 'idn-foundation' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/jkt-48.png', link: 'https://www.jkt48.com', alt: 'jkt-48' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/idn-research.png', link: 'https://research.idntimes.com', alt: 'idn-research' },
                ],
                [
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/ims.png', link: 'https://www.imgs.idntimes.com', alt: 'idn-images' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/fortune-summit.png', link: 'https://www.fortunesummit.fortuneidn.com', alt: 'fortune-summit' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/bfa.png', link: 'https://www.beautyfestasia.popbela.com', alt: 'beautyfestasia' },
                    { img: 'https://cdn.idntimes.com/assets/channels/logo/indonesia-memasak.png', link: 'https://www.idn.media/product', alt: 'indonesia-memasak' },
                ]
            ],
            prevScrollPos: window.pageYOffset,
            isHeaderExpanded: true,
        }
    },
    components: {
        Button
    },
    methods: {
        openDropdown() {
            this.dropdownOpened = !this.dropdownOpened
        },
        handleScroll() {
            const currentScrollPos = window.pageYOffset;
            if (currentScrollPos > this.prevScrollPos) {
                // Скролл вниз
                this.isHeaderExpanded = false;
            } else {
                // Скролл вверх
                this.isHeaderExpanded = true;
            }
            this.prevScrollPos = currentScrollPos;
        }
    },
    mounted() {
        // Добавляем обработчик события скролла при монтировании компонента
        window.addEventListener('scroll', this.handleScroll);
    },
    destroyed() {
        // Удаляем обработчик события скролла при размонтировании компонента
        window.removeEventListener('scroll', this.handleScroll);
    }
}
</script>

<template>
    <header class="header">
        <div class="header__top container">
            <div :class="['header__box1', { 'header__box1-collapsed': !isHeaderExpanded }]">
                <a class="header__logo-link" href="https://www.idntimes.com">
                    <img src="/images/idntimes.png" alt="IDN Times">
                </a>
                <ul class="header__menu">
                    <li>
                        <i class="search-icon"></i>

                    </li>
                    <li>
                        <Button />
                    </li>
                    <li>
                        <button class="dropdown-channels__btn" @click="openDropdown">
                            <svg class="channels" width="20" height="19" viewBox="0 0 20 19" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M5.82031 1.6875V4.8125C5.82031 5.35938 5.39062 5.75 4.88281 5.75H0.9375C0.390625 5.75 0 5.35938 0 4.8125V1.6875C0 1.17969 0.390625 0.75 0.9375 0.75H4.88281C5.39062 0.75 5.82031 1.17969 5.82031 1.6875ZM12.8906 11.0625C12.8906 11.6094 12.4609 12 11.9531 12H8.00781C7.5 12 7.07031 11.6094 7.07031 11.0625V7.9375C7.07031 7.42969 7.5 7 8.00781 7H11.9531C12.4609 7 12.8906 7.42969 12.8906 7.9375V11.0625ZM14.1406 1.6875C14.1406 1.17969 14.5703 0.75 15.0781 0.75H19.0625C19.5703 0.75 20 1.17969 20 1.6875V4.8125C20 5.35938 19.5703 5.75 19.0625 5.75H15.0781C14.5703 5.75 14.1406 5.35938 14.1406 4.8125V1.6875ZM12.8906 4.8125C12.8906 5.35938 12.4609 5.75 11.9531 5.75H8.00781C7.5 5.75 7.07031 5.35938 7.07031 4.8125V1.6875C7.07031 1.17969 7.5 0.75 8.00781 0.75H11.9531C12.4609 0.75 12.8906 1.17969 12.8906 1.6875V4.8125ZM4.88281 7C5.39062 7 5.82031 7.42969 5.82031 7.9375V11.0625C5.82031 11.6094 5.39062 12 4.88281 12H0.9375C0.390625 12 0 11.6094 0 11.0625V7.9375C0 7.42969 0.390625 7 0.9375 7H4.88281ZM0 14.1875C0 13.6797 0.390625 13.25 0.9375 13.25H4.88281C5.39062 13.25 5.82031 13.6797 5.82031 14.1875V17.3125C5.82031 17.8594 5.39062 18.25 4.88281 18.25H0.9375C0.390625 18.25 0 17.8594 0 17.3125V14.1875ZM15.0781 12C14.5703 12 14.1406 11.6094 14.1406 11.0625V7.9375C14.1406 7.42969 14.5703 7 15.0781 7H19.0625C19.5703 7 20 7.42969 20 7.9375V11.0625C20 11.6094 19.5703 12 19.0625 12H15.0781ZM15.0781 18.25C14.5703 18.25 14.1406 17.8594 14.1406 17.3125V14.1875C14.1406 13.6797 14.5703 13.25 15.0781 13.25H19.0625C19.5703 13.25 20 13.6797 20 14.1875V17.3125C20 17.8594 19.5703 18.25 19.0625 18.25H15.0781ZM7.07031 14.1875C7.07031 13.6797 7.5 13.25 8.00781 13.25H11.9531C12.4609 13.25 12.8906 13.6797 12.8906 14.1875V17.3125C12.8906 17.8594 12.4609 18.25 11.9531 18.25H8.00781C7.5 18.25 7.07031 17.8594 7.07031 17.3125V14.1875Z" />
                            </svg>
                        </button>
                        <menu v-if="dropdownOpened" class="dropdown-channels">
                            <p class="dropdown-channels__text">Channels</p>
                            <ul class="dropdown-channels__ul" v-for="channelsGroup in channels">
                                <li v-for="channel in channelsGroup">
                                    <a :href="channel.link">
                                        <img :src="channel.img" alt="">
                                    </a>
                                </li>
                            </ul>
                        </menu>
                    </li>
                </ul>
            </div>
            <nav class="header__box2">
                <ul class="header__box2-ul">
                    <li class="header__box2-item" v-for="page in pages">
                        <a :href="page.link" class="header__link">
                            <span :class="page.active ? 'header__link-active' : ''">{{ page.title }}</span>
                            <img class="header__link-img" :src="page.img" v-if="page.img">
                            <svg class="header__link-svg" v-if="page.more" width="9" height="5" viewBox="0 0 9 5"
                                fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M1.18011 0H8.20746C8.69965 0 8.94574 0.601562 8.59027 0.957031L5.09027 4.45703C4.87152 4.67578 4.51605 4.67578 4.2973 4.45703L0.797302 0.957031C0.441833 0.601562 0.687927 0 1.18011 0Z" />
                            </svg>
                        </a>
                        <div v-if="page.more && page.more.length === 1" class="dropdown-menu">
                            <div v-for="item in page.more" class="dropdown-menu__item">
                                <span class="dropdown-menu__item-type">{{ item.type }}</span>
                                <ul class="dropdown-menu__item-list">
                                    <li v-for="pageItem in item.pages">
                                        <a>{{ pageItem }}</a>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <div v-if="page.more && page.more.length === 2" class="dropdown-menu">
                            <div v-for="item in page.more" class="dropdown-menu__item dropdown-menu__items">
                                <span class="dropdown-menu__item-type">{{ item.type }}</span>
                                <ul class="dropdown-menu__item-list">
                                    <li v-for="pageItem in item.pages">
                                        <a>{{ pageItem }}</a>
                                    </li>
                                </ul>
                            </div>
                            <div class="download-box">
                                <p class="download-box__text">DOWNLOAD IDN APP SEKARANG!</p>
                                <a class="download-box__link" href=""><img
                                        src="https://www.idntimes.com/assets/img/icons/app-download.png"
                                        alt="Google Play"></a>
                                <a class="download-box__link" href=""><img
                                        src="https://www.idntimes.com/assets/img/icons/itunes-download.png"
                                        alt="iTunes"></a>
                            </div>
                        </div>
                    </li>
                </ul>
            </nav>
        </div>
        <div class="header__bottom">
            <div class="header__bottom-wrapper container">
                <span class="tranding">
                    Trending
                </span>
                <div class="slider">
                    <span>Bareskrim Panggil Kembali Panji Gumilang Al Zaytun Besok</span>
                </div>
                <div class="controls">
                    <button class="controls__btn controls__btn-left">
                        <svg width="11" height="19" viewBox="0 0 11 19" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M10.6328 10.1641L3.05469 17.7812C2.66406 18.1328 2.07812 18.1328 1.72656 17.7812L0.828125 16.8828C0.476562 16.5312 0.476562 15.9453 0.828125 15.5547L6.84375 9.5L0.828125 3.48438C0.476562 3.09375 0.476562 2.50781 0.828125 2.15625L1.72656 1.25781C2.07812 0.90625 2.66406 0.90625 3.05469 1.25781L10.6328 8.875C10.9844 9.22656 10.9844 9.8125 10.6328 10.1641Z" />
                            <path
                                d="M10.6328 10.1641L9.9257 9.45695L9.92389 9.45878L10.6328 10.1641ZM3.05469 17.7812L3.72365 18.5245L3.74415 18.5061L3.76361 18.4865L3.05469 17.7812ZM0.828125 15.5547L0.118734 14.8499L0.10134 14.8674L0.0848309 14.8857L0.828125 15.5547ZM6.84375 9.5L7.55314 10.2048L8.25568 9.49771L7.55086 8.79289L6.84375 9.5ZM0.828125 3.48438L0.0848309 4.15334L0.102423 4.17289L0.121018 4.19148L0.828125 3.48438ZM3.05469 1.25781L3.76361 0.552526L3.74415 0.532971L3.72365 0.514518L3.05469 1.25781ZM10.6328 8.875L9.92389 9.58029L9.92571 9.58211L10.6328 8.875ZM9.92389 9.45878L2.34577 17.076L3.76361 18.4865L11.3417 10.8693L9.92389 9.45878ZM2.38572 17.038C2.3766 17.0462 2.37167 17.0449 2.37598 17.0449C2.37849 17.0449 2.38589 17.0454 2.39709 17.0498C2.40906 17.0546 2.42236 17.0628 2.43367 17.0741L1.01946 18.4884C1.78079 19.2497 2.97411 19.1991 3.72365 18.5245L2.38572 17.038ZM2.43367 17.0741L1.53523 16.1757L0.121018 17.5899L1.01946 18.4884L2.43367 17.0741ZM1.53523 16.1757C1.54655 16.187 1.55479 16.2003 1.55955 16.2123C1.56401 16.2235 1.56445 16.2309 1.56445 16.2334C1.56445 16.2377 1.56321 16.2328 1.57142 16.2237L0.0848309 14.8857C-0.589757 15.6353 -0.640318 16.8286 0.121018 17.5899L1.53523 16.1757ZM1.53752 16.2595L7.55314 10.2048L6.13436 8.79519L0.118734 14.8499L1.53752 16.2595ZM7.55086 8.79289L1.53523 2.77727L0.121018 4.19148L6.13664 10.2071L7.55086 8.79289ZM1.57142 2.81541C1.56321 2.80629 1.56445 2.80136 1.56445 2.80566C1.56445 2.80818 1.56401 2.81558 1.55955 2.82677C1.55479 2.83874 1.54655 2.85204 1.53523 2.86336L0.121018 1.44914C-0.640318 2.21048 -0.589757 3.4038 0.0848309 4.15334L1.57142 2.81541ZM1.53523 2.86336L2.43367 1.96492L1.01946 0.550706L0.121018 1.44914L1.53523 2.86336ZM2.43367 1.96492C2.42236 1.97623 2.40906 1.98448 2.39709 1.98924C2.38589 1.9937 2.37849 1.99414 2.37598 1.99414C2.37167 1.99414 2.3766 1.9929 2.38572 2.00111L3.72365 0.514518C2.97411 -0.16007 1.78079 -0.21063 1.01946 0.550706L2.43367 1.96492ZM2.34577 1.9631L9.92389 9.58029L11.3417 8.16971L3.76361 0.552526L2.34577 1.9631ZM9.92571 9.58211C9.90169 9.55809 9.89648 9.53252 9.89648 9.51953C9.89648 9.50655 9.90169 9.48097 9.92571 9.45696L11.3399 10.8712C12.082 10.1291 12.082 8.90998 11.3399 8.16789L9.92571 9.58211Z"
                                fill="white" />
                        </svg>
                    </button>
                    <button class="controls__btn controls__btn-right">
                        <svg width="11" height="19" viewBox="0 0 11 19" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M10.6328 10.1641L3.05469 17.7812C2.66406 18.1328 2.07812 18.1328 1.72656 17.7812L0.828125 16.8828C0.476562 16.5312 0.476562 15.9453 0.828125 15.5547L6.84375 9.5L0.828125 3.48438C0.476562 3.09375 0.476562 2.50781 0.828125 2.15625L1.72656 1.25781C2.07812 0.90625 2.66406 0.90625 3.05469 1.25781L10.6328 8.875C10.9844 9.22656 10.9844 9.8125 10.6328 10.1641Z" />
                            <path
                                d="M10.6328 10.1641L9.9257 9.45695L9.92389 9.45878L10.6328 10.1641ZM3.05469 17.7812L3.72365 18.5245L3.74415 18.5061L3.76361 18.4865L3.05469 17.7812ZM0.828125 15.5547L0.118734 14.8499L0.10134 14.8674L0.0848309 14.8857L0.828125 15.5547ZM6.84375 9.5L7.55314 10.2048L8.25568 9.49771L7.55086 8.79289L6.84375 9.5ZM0.828125 3.48438L0.0848309 4.15334L0.102423 4.17289L0.121018 4.19148L0.828125 3.48438ZM3.05469 1.25781L3.76361 0.552526L3.74415 0.532971L3.72365 0.514518L3.05469 1.25781ZM10.6328 8.875L9.92389 9.58029L9.92571 9.58211L10.6328 8.875ZM9.92389 9.45878L2.34577 17.076L3.76361 18.4865L11.3417 10.8693L9.92389 9.45878ZM2.38572 17.038C2.3766 17.0462 2.37167 17.0449 2.37598 17.0449C2.37849 17.0449 2.38589 17.0454 2.39709 17.0498C2.40906 17.0546 2.42236 17.0628 2.43367 17.0741L1.01946 18.4884C1.78079 19.2497 2.97411 19.1991 3.72365 18.5245L2.38572 17.038ZM2.43367 17.0741L1.53523 16.1757L0.121018 17.5899L1.01946 18.4884L2.43367 17.0741ZM1.53523 16.1757C1.54655 16.187 1.55479 16.2003 1.55955 16.2123C1.56401 16.2235 1.56445 16.2309 1.56445 16.2334C1.56445 16.2377 1.56321 16.2328 1.57142 16.2237L0.0848309 14.8857C-0.589757 15.6353 -0.640318 16.8286 0.121018 17.5899L1.53523 16.1757ZM1.53752 16.2595L7.55314 10.2048L6.13436 8.79519L0.118734 14.8499L1.53752 16.2595ZM7.55086 8.79289L1.53523 2.77727L0.121018 4.19148L6.13664 10.2071L7.55086 8.79289ZM1.57142 2.81541C1.56321 2.80629 1.56445 2.80136 1.56445 2.80566C1.56445 2.80818 1.56401 2.81558 1.55955 2.82677C1.55479 2.83874 1.54655 2.85204 1.53523 2.86336L0.121018 1.44914C-0.640318 2.21048 -0.589757 3.4038 0.0848309 4.15334L1.57142 2.81541ZM1.53523 2.86336L2.43367 1.96492L1.01946 0.550706L0.121018 1.44914L1.53523 2.86336ZM2.43367 1.96492C2.42236 1.97623 2.40906 1.98448 2.39709 1.98924C2.38589 1.9937 2.37849 1.99414 2.37598 1.99414C2.37167 1.99414 2.3766 1.9929 2.38572 2.00111L3.72365 0.514518C2.97411 -0.16007 1.78079 -0.21063 1.01946 0.550706L2.43367 1.96492ZM2.34577 1.9631L9.92389 9.58029L11.3417 8.16971L3.76361 0.552526L2.34577 1.9631ZM9.92571 9.58211C9.90169 9.55809 9.89648 9.53252 9.89648 9.51953C9.89648 9.50655 9.90169 9.48097 9.92571 9.45696L11.3399 10.8712C12.082 10.1291 12.082 8.90998 11.3399 8.16789L9.92571 9.58211Z"
                                fill="white" />
                        </svg>
                    </button>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang='scss' scoped>
.header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 10;
    background-color: #fff;

    &__top {
        position: relative;
    }

    &__bottom {
        position: absolute;
        z-index: 1;
        border-top: 1px solid #eee;
        width: 100%;
        background-color: #fff;

        &-wrapper {
            display: flex;
            font-family: "Poppins", sans-serif;

            .tranding {
                font-weight: 700;
                color: #ed2126;
                font-size: 12px;
                padding: 11px 35px;
                border: 1px solid #e5e5e4;
                border-top: none;
                overflow: hidden;
            }

            .slider {
                font-size: 14px;
                color: #333;
                border-bottom: 1px solid #e5e5e4;
                display: flex;
                align-items: center;
                padding: 0 10px;
                width: calc(100% - 228px);
            }

            .controls {
                display: flex;
                gap: 20px;
                border: 1px solid #e5e5e4;
                border-top: none;
                padding: 8px 20px;

                &__btn {
                    background-color: transparent;
                    border: none;
                    cursor: pointer;
                    display: flex;
                    align-items: center;

                    svg {
                        fill: #ED2126;
                    }

                    &:hover {
                        svg {
                            fill: #E5E5E4;
                        }
                    }

                    &-left {
                        transform: rotate(180deg);
                    }

                    &-right {}
                }
            }
        }
    }

    &__box1 {
        height: 48px;
        margin: 30px 0 25px 0;
        display: flex;
        align-items: center;
        justify-content: space-between;

        transition: all 0.3s ease;

        &-collapsed {
            overflow: hidden;
            height: 0;
            margin: 0;
        }
    }



    &__box2 {
        margin-top: 30px;

        &-ul {
            list-style: none;
            width: 100%;
            display: flex;
            justify-content: space-between;
            padding: 0;
            margin: 0;
            gap: 12px;
            overflow: auto;

            &::-webkit-scrollbar {
                height: 3px;

                &-track {
                    background-color: transparent;
                }

                &-thumb {
                    background-color: #888;
                    border-radius: 3px;
                }
            }
        }

        &-item {
            height: 50px;

            &:hover .dropdown-menu {
                display: flex;
            }
        }
    }

    &__link {
        color: #333;
        text-decoration: none;
        font-family: "Poppins", sans-serif;
        font-size: 14px;
        font-weight: bold;
        text-transform: uppercase;
        display: flex;
        align-items: center;
        gap: 4px;

        &-active {
            color: #ed2126;
        }

        &-img {
            height: 18px;
            width: 18px;
        }

        &-svg {
            fill: #333333;

        }

        &:hover {
            color: #ed2126;

            svg {
                fill: #ed2126;
            }
        }

        &:hover+&-svg {
            fill: #ed2126;

        }
    }

    &__menu {
        list-style: none;
        display: flex;
        align-items: center;
        gap: 14px;
        position: relative;

        li {
            display: flex;
            align-items: center;
            justify-content: center;

            .search-icon {
                display: block;
                width: 24px;
                height: 24px;
                background-image: url("/images/search.png");
                /* Путь к вашему PNG изображению */
                background-size: cover;
                background-position: center;
                cursor: pointer;

                &:hover {
                    background-image: url("/images/search-red.png");
                }
            }

            .channels {
                fill: #ED2126;
                cursor: pointer;

                &:hover {
                    fill: #b30f13;
                }
            }
        }
    }

    &__logo-link {
        img {
            width: 120px;
            height: 20px;
        }
    }
}


.dropdown {
    &-menu {
        position: absolute;
        z-index: 2;
        display: none;
        left: 0;
        width: 100%;
        padding: 30px;
        background: #fff;
        box-shadow: 0 8px 16px rgba(170, 170, 170, .29);
        border-radius: 4px;
        flex-wrap: wrap;


        &__item {
            display: flex;
            flex-direction: column;
            font-family: "Poppins", sans-serif;
            font-weight: 700;

            &-type {
                font-size: 12px;
                color: #777;


            }

            &-list {
                list-style: none;
                padding: 0;
                display: flex;
                flex-wrap: wrap;


                li {
                    width: 25%;
                    color: #333;
                    font-size: 14px;
                    padding: 15px 0 0;
                    text-transform: uppercase;
                    cursor: pointer;

                    &:hover {
                        color: #ed2126;
                    }
                }
            }
        }

        &__items {
            width: 50%;

            &:nth-child(1) {
                .dropdown-menu__item-list {
                    li {
                        width: 50%;

                    }
                }
            }

            &:nth-child(2) {
                border-left: 1px solid #eee;
                padding-left: 12px;

                .dropdown-menu__item-list {
                    li {
                        width: 100%;

                    }
                }
            }

        }

        .download-box {
            padding-top: 25px;
            margin-top: 25px;
            border-top: 1px solid #eee;
            display: flex;
            justify-content: end;
            align-items: center;
            width: 100%;
            gap: 10px;
            height: 68px;

            &__text {
                line-height: 40px;
                font-size: 18px;
                font-family: "Poppins", sans-serif;
                font-weight: 700;
            }

            &__link {
                display: flex;
                align-items: center;

                img {
                    max-width: 135px;
                }
            }
        }
    }

    &-channels {
        position: absolute;
        z-index: 3;
        top: 100%;
        right: 0;
        min-width: 580px;
        background: #fff;
        box-shadow: 0 8px 16px rgba(170, 170, 170, .29);
        border: 1px solid rgba(0, 0, 0, .05);
        max-height: calc(100vh - 48px);
        border-radius: 4px 4px;
        overflow-y: auto;
        overflow-x: hidden;
        padding: 20px 25px;

        &__btn {
            border: none;
            background-color: transparent;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        &__text {
            margin: 0 0 15px;
            font-family: "Poppins", sans-serif;
            font-weight: 700;
            font-size: 12px;
            color: #777;
        }

        &__ul {
            list-style: none;
            padding: 10px 0;
            display: flex;
            flex-wrap: wrap;
            gap: 15px;

            &:nth-child(3) {
                row-gap: 5px;
                column-gap: 15px;
                max-width: 460px;
            }

            &:nth-child(n + 3) {
                border-top: 1px solid #eee;
            }
        }
    }
}


@media (max-width: 768px) {
    .header {
        &__box2 {

            &-ul {
                padding-bottom: 5px;
            }

            &-item {
                height: auto;
            }
        }

        &__bottom {
            display: none;
        }
    }

    .dropdown {
        &-channels {
            min-width: 355px;
        }
    }
}

@media (max-width: 550px) {
    .dropdown {
        &-menu {
            &:hover {
                display: flex;
            }

            flex-direction: column;

            &__items {
                width: 100%;

                &:nth-child(1) {
                    padding: 0 0 10px;
                }

                &:nth-child(2) {
                    border-left: none;
                    padding: 10px 0 0;
                    border-top: 1px solid #eee;
                }

                .dropdown-menu__item-list {
                    width: 100%;
                }
            }

            .download-box {
                display: none;
            }
        }
    }
}</style>