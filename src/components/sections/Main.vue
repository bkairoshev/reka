<script setup>
import Menu from '../ui/Menu.vue';
import LogoWhite from '../icons/LogoWhite.vue';
</script>

<template>
    <section class="sec-main">
        <Menu />

        <div class="sec-main--inner">
            <LogoWhite class="sec-main--logo" />

            <div class="sec-main--title">
                <h1>теплицы <br /> регионов</h1>

                <span>
                    Тепличные комплексы <br>
                    современного <br>
                    поколения <br>
                </span>
            </div>

            <div class="sec-main--button">
                <img src="../../assets/icons/quality.svg" />
                <button class="btn">О компании</button>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
.sec-main {
    background: url('../../assets/images/tr-main.png') no-repeat;
    background-size: cover;
    width: 100%;
    height: 100vh;

    &--logo {
        display: none;
    }

    &--inner {
        display: grid;
        align-content: space-between;
        padding: 24px;
    }

    &--title {
        display: grid;
        gap: 10px;
    }

    &--title>span {
        font-size: 18px;
        line-height: 24px;
    }

    &--title>h1 {
        text-transform: uppercase;
        font-weight: 500;
        font-size: 34px;
        line-height: 44px;
    }

    &--button {
        justify-self: start;

        display: grid;
        justify-items: center;
        align-content: end;
        gap: 20px;
    }
}


@media (min-width: 640px) {
    .sec-main {
        display: grid;
        grid-template-columns: 120px 1fr;

        &--logo {
            display: block;
            width: 135px;
            height: 93px;
        }

        &--inner {
            border-left: 1px solid #F0F0F066;
            padding: 31px 60px;
            display: grid;
        }

        &--title {
            grid-auto-flow: column;
            gap: 30px;
            justify-content: start;
            align-content: end;
            align-items: end;
        }

        &--title>span {
            font-size: 24px;
            line-height: 30px;
            padding-bottom: 20px;
        }

        &--title>h1 {
            font-size: 115px;
            line-height: 130px;
        }

        &--button {
            justify-self: end;
        }
    }
}

@media (min-width: 768px) {}
</style>
