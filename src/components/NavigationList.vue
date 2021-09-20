<template>
    <div class="navigationList">

        <ul>
            <li><router-link to="/" class="link-to-page">Home</router-link></li>
            <li><router-link to="/marketplace" class="link-to-page">Marketplace</router-link></li>
            <li><a class="link-to-page" href="/community">Community</a> </li>
        </ul>

        <div class="socialMedia">
            <i class="fab fa-facebook"></i> |
            <i class="fab fa-instagram"></i>
        </div>
    </div>
</template>

<script>
export default {
    name: 'NavigationList'
}
</script>

<style scoped>

.navigationList {
    display: flex;
    flex-direction: column;
}

ul {
    list-style: none;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 0px;
    margin-bottom: 5px;
    padding: 0px;
}

li, .link-to-page {
    display: inline-block;
    color: #fff;
    font-size: min(3vw, 30px);
    font-weight: bold;
    margin-left: 0.4rem;
    margin-right: 0.4rem;
    margin-bottom: 0px;
    cursor: pointer;
}

li:hover {
    color: #2c3e50;
    }

.socialMedia {
    font-size: 1.3rem;
}

</style>


