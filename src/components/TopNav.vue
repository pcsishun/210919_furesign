<template>
    <div class="TopNav">
        <div class="logo">
            <img 
                src="../assets/furesign_icon.png" 
                alt="FuResign"/>
            <h1> FuResign </h1>
        </div>

        <div class="routerIcon" @click="showNav = !showNav">
            <i class="fas fa-bars"></i>
        </div>

        <div class="router">
            <router-link to="/">Home</router-link> |
            <router-link to="/marketplace">Marketplace</router-link>
        </div>
    </div>

    <NavigationList class="navList"/>

    <div class="contentApp" :class="{'open':showNav}">
      <router-view/>
    </div>
</template>

<script>

import NavigationList from '@/components/NavigationList.vue'

export default {
    name: "TopNav",
    components: {
        NavigationList
    },
    data: () => {
        return {
            showNav: false
        }
    }
}
</script>

<style scoped>

    @media screen and (min-width: 900px) {
        i {
            display: none !important;
        }
    }

    @media screen and (max-width: 900px) {
        .router {
            display: none !important;
        }
    }

    .navList {
        position: relative;
        top: min(1vw,15px);
    }

    .contentApp {
        transition: 1s transform cubic-bezier(.19,.78,.23,.96);
        transform: translateY(max(-11vw,-65px));
    }

    .open {
        transform: translateY(10px);
    }

    .TopNav {
        background-color: white;
        display: flex;
        flex-wrap: nowrap;
        align-items: center;
        justify-content: space-between;
        padding: 0vw 3.5vw;
        margin: 1vw 1.5vw;
        border-radius: 20px;
        box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
    }

    .logo {
        display: flex;
        align-items: center;
    }

    .routerIcon {
        cursor: pointer;
    }


    img {
        width: min(5vw, 65px);
    }

    h1 {
        font-size: min(3vw, 30px);
        margin-left: 1vw;
        margin-top: 0.5vw;
        margin-bottom: 0.5vw;
    }

    i {
        font-size: 2.5vw;
        color: #2c3e50;
    }

    @media screen and (min-width: 1200px) {
        .TopNav {
        margin: 10px 3.5vw;
        }
        
        h1 {
            margin-left: 10px;
            margin-top: 10px;
            margin-bottom: 10px;
        }

        i {
            font-size: 30px;
        }
    }

    @media screen and (max-width: 600px) {
        img {
            width: 25px;
        }
    }

</style>