<template>
    <footer>
        <img src="../assets/logo.png">

        <ul>
            <li>
                <a href="https://www.linkedin.com/in/vandersandinoo/" target='_blank' ><i class='bx bxl-linkedin-square' style='color:#f5f4f4' ></i></a>
                <a href="https://api.whatsapp.com/send?phone=5581996430492&text=Ol%C3%A1,%20acessei%20link%20pelo%20seu%20portif%C3%B3lio."><i class='bx bxl-whatsapp' target='_blank' style='color:#f5f4f4' ></i></a>
                <a href="https://www.instagram.com/vander_sandino/" target='_blank'><i class='bx bxl-instagram-alt' style='color:#f5f4f4' ></i></a>
                <a href="https://github.com/vandersann" target='_blank'><i class='bx bxl-github'  style='color:#f5f4f4' ></i></a>
            </li>
        </ul>


        <p> &copy; 2023 - Todos os Direitos Reservados.</p>

    </footer>
</template>

<script>
export default {
    name: "Footer"
}
</script>

<style scoped>
    footer {
        height: 10rem;
        background-color: black;
        color: white;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        width: 100%;
    }

    ul {
        margin: 0;
		padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    ul li {
        list-style: none;
        margin: 0 10px;
    }

    ul li a {
        display: inline-block;
        height: 50px;
        width: 50px;
        position: relative;
        text-align: center;
        line-height: 56px;
        border-radius: 50%;
        font-size: 30px;
        color: #fff;
        transition: .5s ease-in;
        margin-bottom: .8rem;
    }

    ul li a::before{
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        border-radius: 50%;
        background: #1E88E5;
        transition: .5s;
        transform: scale(.9);
        z-index: -1;
    }

    ul li a:hover::before {
        transform: scale(1.1);
        box-shadow: 0 0 15px #1E88E5;
    }

    ul li a:hover {
        color: #1E88E5;
        box-shadow: 0 0 5px #1E88E5;
        text-shadow: 0 0 5px #1E88E5;
    }


</style>