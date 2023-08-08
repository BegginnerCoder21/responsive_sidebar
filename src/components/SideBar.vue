<template>
    <div>
        <aside :class="{is_expanded_style : is_expanded}">
            <div class="logo" >
                <img src="../../public/favicon.ico" alt="logo" >
            </div>
            <div class="menu-toggle-wrap">
                <button class="menu-toggle" @click="toggle_menu">
                    <span class="material-symbols-outlined">
                        keyboard_double_arrow_right
                    </span>
                </button>
            </div>
            <h3 class="men">Menu</h3>
            <div class="menu">
                <router-link class="button" to="/">
                    <span class="material-symbols-outlined">home</span>
                    <span class="text">Home</span>
                </router-link>
                <router-link class="button" to="/about">
                    <span class="material-symbols-outlined">description</span>
                    <span class="text">About</span>
                </router-link>
                <router-link class="button" to="/team">
                    <span class="material-symbols-outlined">group</span>
                    <span class="text">Team</span>
                </router-link>
                <router-link class="button" to="/contact">
                    <span class="material-symbols-outlined">notification_multiple</span>
                    <span class="text">Contact</span>
                </router-link>
            </div>

            <div class="flex"></div>
            <div class="menu">
                <router-link class="button" to="/settings">
                    <span class="material-symbols-outlined">settings</span>
                    <span class="text">Settings</span>
                </router-link>
            </div>
        </aside>
    </div>
</template>

<script setup lang="ts">
import {ref} from 'vue';

const is_expanded = ref(localStorage.getItem('is_expanded') === 'true')

const toggle_menu = () => {
    is_expanded.value = !is_expanded.value;

    localStorage.setItem('is_expanded',is_expanded.value)
}

</script>

<style scoped>

aside{
    background-color: #1e293b;;
    display: flex;
    color:#f1f5f9;
    flex-direction: column;
    width: calc(2rem + 20px);
    min-height: 100vh;
    padding: 1rem;

    transition: .2s ease-out;

    @media (max-width: 350px) {
		position: absolute;
		z-index: 99;
	}
    
}

.flex{
    flex: 1 1 0;
}

button{
    border: none;
    outline: none;
    background-color: #1e293b;
    cursor: pointer;
    color: #fff;
    transition: .4s ease-out;
    .material-symbols-outlined{
        transition: .10s ease-out;
    }

}
h3,.button .text{
    opacity: 0;
    transition: .3s ease-out;
}

.menu{
    margin: 0 -1rem;
    .button{
        display: flex;
        align-items: center;
        text-decoration: none;
        padding:  0.5rem 0.8rem;

        .material-symbols-outlined,.text{
            transition: .3s ease-out;
            font-size:23px;
            color: #f1f5f9;
        }

        &:hover , &.router-link-exact-active{
            background-color: #334155;

            .material-symbols-outlined,.text{
                color: #4ade80;
            }
        }
        &.router-link-exact-active{
            border-right: 5px solid #4ade80;
        }
    }
}

button:hover{
    .material-symbols-outlined{
        transform: translateX(0.5rem);
        color: #4ade80;
    }
}
.menu-toggle-wrap{
    display: flex;
    justify-content: flex-end;
    position: relative;
    top: 0;
    transition: .2s ease-out;
    padding: 0 1.5rem;
    
    .material-symbols-outlined{
        font-size: 28px;
    }
}
.is_expanded_style{
    width: 220px;
    .menu-toggle-wrap{
        top: -50px;
        margin: 0 -1.5rem;
 
    }
    .menu-toggle{
        transform: rotate(-182deg);
        padding: 0 -1rem;
    }

    .men,.button .text{
        opacity: 1;
    }

    .material-symbols-outlined{
        margin-right: 1rem;
    }
    
}

h3{
    color: #64748b;
    margin-bottom: 0.5rem;
    font-size: 0.875rem ;
    text-transform: uppercase;
}



.logo{
    margin-bottom: 1rem;
    margin-left: -4px ;
   
}

img{
    width: 25px;
}
</style>