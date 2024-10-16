<section class="hero">
    <div class="hero-background" >
        <img src="https://lindastade.com/wp-content/uploads/2022/10/ShutterstockBasic_489605152-1280x640.jpg" alt="">
    </div>
        <img src="https://www.souepl.cz/wp-content/uploads/2022/07/logo_velke_b-3.png" alt="">

    <h1>Střední odborné učiliště, elektrotechnické Plzeň</h1>

    <p>Pojďte stavět vaší budoucnost u nás na škole, kde propojujeme praxi se vzděláváním</p>

    <div class="hero-buttons">
        <a href="/about">Login</a>
        <a href="/" id="ghost">About</a>
    </div>
</section>

<section class="about">
    <h1>Proč studovat u nás?</h1>
    <div class="about-content">
        <img src="https://blogs.staffs.ac.uk/student-blogs/files/2016/08/iStock_28423686_MEDIUM.jpg" alt="">
        <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Quaerat hic iure voluptatibus, quam ut a reprehenderit provident ea debitis voluptatem neque praesentium quas. Nulla temporibus nemo dolore, doloribus veritatis rerum.
        </p>
    </div>
</section>

<style>
    .about{
        width: 100%;
        max-width: 1300px;
        margin: 36px 0;
        padding: 10px;
        box-sizing: border-box;
    }

    .about h1{
        text-align: center;
    }

    .about .about-content{
        display: flex;
        justify-content: center;
        gap: 36px;
        align-items: center;
    }
    .about .about-content img{
        width: 100%;
        max-width: 450px;
    }

    .hero {
        width: 100%;
        min-height: calc(100vh - 100px);
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        position: relative;
        flex-wrap: wrap;
        color: white;
    }

    .hero .hero-background{
        position: absolute;
        top: -100px;
        z-index: -1;
        width: 100%;
        height: 100vh;
        background-color: rgba(22, 21, 21, 0.631);
    }

    .hero .hero-background img{
        width: 100%;
        height: 100%;
        z-index: -1;
        object-fit: cover;
        mix-blend-mode: darken;
    }


    .hero img {
        width: 450px;
    }

    .hero-buttons {
        display: flex;
        gap: 36px;
        flex-wrap: wrap;
    }

    .hero-buttons a {
        color: white;
        background-color: rgb(44, 158, 59);
        text-decoration: none;
        width: 150px;
        height: 50px;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 10px;
        font-weight: 500;
        font-family: Arial, Helvetica, sans-serif;
        transition: ease 0.5s;
    }

    #ghost {
        color: white;
        background: none;
        border: 1px solid white;
        transition: ease 0.5s;
    }

    #ghost:hover {
        color: black;
        background: white;
        border: 1px solid rgba(0, 0, 0, 0);
    }

    .hero-buttons a:hover {
        color: black;
        background: white;
    }
</style>
