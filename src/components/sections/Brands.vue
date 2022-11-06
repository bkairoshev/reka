<script setup>
import Menu from '../ui/Menu.vue';
import LogoWhite from '../icons/LogoWhite.vue';

const indicators = [
    {
        title: "региона выращивания",
        value: 4,
    },
    {
        title: "общая площадь теплиц",
        value: "60 га",
    },
    {
        title: "сотрудников",
        value: "1 300",
    },
    {
        title: "тонн продукции в год",
        value: "55 000",
    },
]
</script>

<template>
    <section class="sec-about">
        <div class="sec-about--inner">
            <div class="sec-about--video">
                <img src="../../assets/images/tr-about.png" alt="">
            </div>
            <div class="sec-about--desc">
                <div class="sec-about--desc--text">
                    «Теплицы Регионов» - группа компаний, создающая и управляющая высокотехнологичными тепличными
                    комплексами для круглогодичного выращивания овощной продукции.
                    Самые передовые и инновационные разработки отрасли круглогодичного выращивания овощной продукции в
                    защищенном (закрытом) грунте апробируются и применяются на производствах компании.
                </div>

                <div class="sec-about--desc--indicators">
                    <div v-for="(item, i) in indicators" :key="i" class="sec-about--desc--indicators--item">
                        <span class="sec-about--desc--indicators--value">{{ item.value }}</span>
                        <span class="sec-about--desc--indicators--title">{{ item.title }}</span>
                    </div>
                </div>

                <button class="sec-about--desc--button btn">
                    Подробнее
                </button>
            </div>


        </div>
    </section>
</template>

<style lang="scss" scoped>
.sec-about {
    width: 100%;
    height: 100vh;

    color: #121715;

    &--inner {
        display: grid;
        grid-template-columns: auto 1fr;
    }

    &--video {
        height: 100vh;
        width: auto;

        img {
            width: 100%;
            height: 100%;
        }
    }

    &--desc {
        padding-left: 120px;

        display: grid;
        align-content: space-around;

        &--text {
            font-size: 18px;
            line-height: 30px;
            max-width: 740px;
        }

        &--indicators {
            display: grid;
            gap: 50px;

            &--item {
                display: grid;
                grid-template-columns: 370px 1fr;
                align-items: center;
            }

            &--title {
                font-size: 24px;
                line-height: 30px;
            }

            &--value {
                font-weight: 700;
                font-size: 70px;
                line-height: 70px;

                color: #F4A62F;
            }
        }
    }
}
</style>
