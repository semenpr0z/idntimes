<script>
export default {
    data() {
        return {
            formattedDate: '',
            yesterdayISO: '',
        };
    },
    mounted() {
        const today = new Date();
        const yesterday = new Date(today);
        yesterday.setDate(today.getDate() - 1);

        this.yesterdayISO = yesterday.toISOString();
        this.formattedDate = this.formatDate(yesterday, 'en');
    },
    methods: {
        formatDate(date, locale) {
            const day = date.toLocaleString(locale, { day: '2-digit' });
            const month = date.toLocaleString(locale, { month: 'short' });
            const year = date.toLocaleString(locale, { year: '2-digit' });
            const time = date.toLocaleString(locale, {
                hour: '2-digit',
                minute: '2-digit',
                hour12: false,
            });

            return `${day} ${month} ${year} | ${time}`;
        },
    },
}
</script>

<template>
    <section class="history-and-date">
        <ul class="history">
            <li class="history__item">
                <a href="">Home</a>
            </li>
            <li class="history__item">
                <a href="">Korea</a>
            </li>
            <li class="history__item">
                <a href="">Kpop</a>
            </li>
            <li class="history__item history__item-active">
                <a>Pro Kontra MV NewJeans Cool With You, Ada Scene Yang Terlalu Vulgar?</a>
            </li>
        </ul>
        <time class="time" :datetime="yesterdayISO">{{ formattedDate }}</time>
    </section>
</template>

<style lang='scss' scoped>
.history-and-date {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    max-width: 765px;
    padding: 10px 0;

    .history {
        list-style: none;
        margin: 0;
        padding: 0;
        font-size: 13px;
        color: #333;
        display: flex;
        align-items: center;


        &__item {
            a {
                color: #333;
                text-decoration: none;
            }

            &:nth-child(n+2) {
                &::before {
                    content: "\203A";
                    font-size: 15px;
                    color: #333;
                    padding: 0 5px;
                }
            }

            &-active {
                a {
                    color: #ed2126;
                }
            }
        }
    }

    .time {
        color: gray;
        font-size: 15px;
    }
}

@media (max-width: 1000px) {
    .history-and-date {
        max-width: 100%;

        .history {


            &__item {
                text-transform: uppercase;
                font-size: 16px;

                &:nth-child(n+2) {
                    &::before {
                        font-weight: 900;
                    }
                }

                &:nth-last-child(2) {
                    a {
                        color: #ed2126;
                    }
                }

                &-active {
                    display: none;
                }
            }
        }

        .time {
            display: none;
        }
    }
}
</style>