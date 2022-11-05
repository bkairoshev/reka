<template>
    <div>
        <svg class="icon" width="30" height="50" viewBox="0 0 30 50" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect x="10" y="50" width="33" height="3" transform="rotate(-90 10 50)" fill="white" />
            <rect x="16.667" y="50" width="50" height="3" transform="rotate(-90 16.667 50)" fill="white" />
        </svg>
        <svg class="icon-mobile" width="50" height="30" viewBox="0 0 50 30" fill="none"
            xmlns="http://www.w3.org/2000/svg">
            <rect width="33" height="3" transform="matrix(-1 0 0 1 50 10)" fill="white" />
            <rect width="50" height="3" transform="matrix(-1 0 0 1 50 16.667)" fill="white" />
        </svg>
    </div>
</template>

<style lang="scss" scoped>
.icon {
    display: none;
}

.icon-mobile {
    display: block;
}

@media (min-width: 640px) {
    .icon {
        display: block;
    }

    .icon-mobile {
        display: none;
    }
}
</style>
    