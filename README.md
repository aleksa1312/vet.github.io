<!DOCTYPE html>
<html lang="sr">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VetCare - Veterinarska Ordinacija</title>
    <style>
        {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #333;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        nav {
            background: #1a5c2e;
            padding: 15px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        nav .logo {
            font-size: 24px;
            font-weight: bold;
            color: white;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        nav .logo span {
            color: #8ee4af;
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 25px;
        }

        nav ul li a {
            color: white;
            font-size: 15px;
            font-weight: 500;
            transition: color 0.3s;
            padding: 5px 0;
        }

        nav ul li a:hover {
            color: #8ee4af;
        }

        .hamburger {
            display: none;
            font-size: 28px;
            color: white;
            cursor: pointer;
        }

        .hero {
            background: linear-gradient(rgba(26, 92, 46, 0.8), rgba(26, 92, 46, 0.6)),
                url('data:image/jpeg;base64,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') center/cover;
            min-height: 85vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            padding: 40px 20px;
        }

        .hero-content h1 {
            font-size: 52px;
            margin-bottom: 20px;
            text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.3);
        }

        .hero-content h1 span {
            color: #8ee4af;
        }

        .hero-content p {
            font-size: 20px;
            max-width: 600px;
            margin: 0 auto 30px;
            line-height: 1.6;
            opacity: 0.9;
        }

        .btn {
            display: inline-block;
            padding: 14px 32px;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            border: none;
        }

        .btn-primary {
            background: #8ee4af;
            color: #1a5c2e;
        }

        .btn-primary:hover {
            background: #6dd89a;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .btn-outline {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        .btn-outline:hover {
            background: white;
            color: #1a5c2e;
            transform: translateY(-2px);
        }


        section {
            padding: 80px 40px;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 36px;
            color: #1a5c2e;
            margin-bottom: 10px;
        }

        .section-title p {
            color: #666;
            font-size: 17px;
            max-width: 550px;
            margin: 0 auto;
        }

        .cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 25px;
            max-width: 1100px;
            margin: 0 auto;
        }

        .card {
            background: white;
            border-radius: 12px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s, box-shadow 0.3s;
            border: 1px solid #eee;
        }

        .card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.12);
        }

        .card-icon {
            width: 65px;
            height: 65px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 18px;
            font-size: 28px;
        }

        .card h3 {
            font-size: 20px;
            margin-bottom: 10px;
            color: #1a5c2e;
        }

        .card p {
            color: #666;
            font-size: 14px;
            line-height: 1.6;
        }

        .card .price {
            margin-top: 12px;
            font-weight: bold;
            color: #1a5c2e;
            font-size: 16px;
        }

        .gallery {
            background: #f0f7f2;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 15px;
            max-width: 1100px;
            margin: 0 auto;
        }

        .gallery-grid img {
            width: 100%;
            height: 220px;
            object-fit: cover;
            border-radius: 10px;
            transition: transform 0.3s;
            cursor: pointer;
        }

        .gallery-grid img:hover {
            transform: scale(1.03);
        }

        .work-hours {
            background: white;
        }

        .hours-container {
            max-width: 600px;
            margin: 0 auto;
            background: #f0f7f2;
            border-radius: 12px;
            padding: 35px;
        }

        .hours-row {
            display: flex;
            justify-content: space-between;
            padding: 12px 0;
            border-bottom: 1px solid #d4ead9;
            font-size: 16px;
        }

        .hours-row:last-child {
            border-bottom: none;
        }

        .hours-row .day {
            font-weight: 600;
            color: #1a5c2e;
        }

        .hours-row .time {
            color: #555;
        }

        .emergency {
            margin-top: 25px;
            background: #dc2626;
            color: white;
            padding: 15px;
            border-radius: 8px;
            text-align: center;
            font-weight: 600;
        }

        .contact {
            background: #f0f7f2;
        }

        .contact-wrapper {
            max-width: 900px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: start;
        }

        .contact-info h3 {
            font-size: 22px;
            color: #1a5c2e;
            margin-bottom: 20px;
        }

        .contact-info p {
            margin-bottom: 15px;
            color: #555;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .contact-form {
            background: white;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.08);
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 12px 15px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 8px;
            font-size: 15px;
            font-family: inherit;
            transition: border-color 0.3s;
        }

        .contact-form input:focus,
        .contact-form textarea:focus {
            outline: none;
            border-color: #1a5c2e;
        }

        .contact-form textarea {
            height: 120px;
            resize: vertical;
        }

        .contact-form button {
            width: 100%;
            padding: 14px;
            background: #1a5c2e;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: background 0.3s;
        }

        .contact-form button:hover {
            background: #145a28;
        }


        footer {
            background: #1a5c2e;
            color: white;
            text-align: center;
            padding: 25px;
            font-size: 14px;
        }

        .toast {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: #1a5c2e;
            color: white;
            padding: 16px 24px;
            border-radius: 10px;
            font-weight: 500;
            display: none;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
        }

        p {
            color: white;
        }
    </style>
</head>

<body>


    <nav>
        <div class="logo">🐾 Vet<span>Care</span></div>
        <p>Uradjeno koristeci chatgpt kao alatku</p>
        <ul id="navMenu">
            <li><a href="#pocetna">Pocetna</a></li>
            <li><a href="#usluge">Usluge</a></li>
            <li><a href="#galerija">Galerija</a></li>
            <li><a href="#radno-vreme">Radno vreme</a></li>
            <li><a href="#kontakt">Kontakt</a></li>
        </ul>
    </nav>
    <section class="hero" id="pocetna">
        <div class="hero-content">
            <h1>Zdravlje vasih ljubimaca je nas <span>prioritet</span></h1>
            <p>Pruzamo vrhunsku veterinarsku negu sa ljubavlju i paznjom.Vasi krzneni prijatelji zasluzuju najbolje!</p>
            <a href="#kontakt" class="btn btn-primary">Zakazite pregled</a>
            <a href="#usluge" class="btn btn-outline" style="margin-left:10px;">Nase usluge</a>
        </div>
    </section>
    <section id="usluge">
        <div class="section-title">
            <h2>Nase usluge</h2>
            <p>Kompletna veterinarska nega za vase ljubimce pod jednim krovom</p>
        </div>
        <div class="cards">
            <div class="card">
                <div class="card-icon" style="background:#e8f5e9;">💉</div>
                <h3>Vakcinacija</h3>
                <p>Kompletna zaštita vaseg ljubimca svim potrebnim vakcinama po najnovijim protokolima.</p>
                <div class="price">od 2.500 RSD</div>
            </div>
            <div class="card">
                <div class="card-icon" style="background:#fff3e0;">🩺</div>
                <h3>Pregledi</h3>
                <p>Redovni sistematski pregledi i detaljna dijagnostika uz modernu opremu.</p>
                <div class="price">od 1.500 RSD</div>
            </div>
            <div class="card">
                <div class="card-icon" style="background:#fce4ec;">🚑</div>
                <h3>Hitne intervencije</h3>
                <p>Dostupni 24/7 za hitne slucajeve. Brza pomoc kada je najpotrebnija.</p>
                <div class="price" style="color:#dc2626;">Pozovite odmah!</div>
            </div>
            <div class="card">
                <div class="card-icon" style="background:#e8eaf6;">✂️</div>
                <h3>Hirurgija</h3>
                <p>Sve vrste hirurskih zahvata sa modernom anestezijom i postoperativnom negom.</p>
                <div class="price">od 5.000 RSD</div>
            </div>
        </div>
    </section>

    <!-- GALERIJA -->
    <section class="gallery" id="galerija">
        <div class="section-title">
            <h2>Nasi pacijenti</h2>
            <p>Upoznajte neke od nasih najdrazih pacijenata</p>
        </div>
        <div class="gallery-grid">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRReHY92FWuA2OOqrdLNZqO8EmG3fPGWj3YmgDRiEZu8gPscjncPtc75gy6O1Z2BGV8HYa9mTGcuHCIHA8ZO9OXUuXPFMcuTf9YQsygbfJb&s=10"
                alt="Pas">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTCjyWzQwVPY5xissRqD4eIqlzzi9V48wKDQVBaJthcMeDSe1cl-hiPtjX5LNyiNRPIlasGInPAoXm-5fSIwemD2CHiibK3tpaJo_ift9eZ&s=10"
                alt="Macka">
            <img src="data:image/jpeg;base64,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"
                alt="Stene">
            <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBxMTEhITExMVFRUXFhUVFxgVGBcYFRUYFRUXFhUVFRYYHSggGBolGxUVITEhJSkrLi4uFx8zODMtNygtLisBCgoKDg0OGxAQGy0lICUtLS0tKy0wLS0uLS0tNS0tLy0tKy0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLf/AABEIAOEA4QMBIgACEQEDEQH/xAAbAAEAAwADAQAAAAAAAAAAAAAAAwQFAQIGB//EADYQAAIBAwIEBAQFBAIDAQAAAAABAgMEESExBRJBUWGBkfAGInGhEzKxwdEUUuHxQoIVI8IH/8QAGQEBAAMBAQAAAAAAAAAAAAAAAAIDBAEF/8QAJBEAAwADAAICAgIDAAAAAAAAAAECAxEhEjEEQRMiMrEUUWH/2gAMAwEAAhEDEQA/APuIAAAAAAAAAAAAAAAAAAAAAAAABDXr8v1AJgRUK3MSgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAHDZXneRRxtL2dSbJ5ywm3sjMlUy2+/tIq8R4upSjSj1fzPwWrR3UyCyKnws8GvZLRrYkmayZ5yrX2Zu2k8xR2WMk6SZOACZUAAAAAAAAAAAAAAAAAAAAAAAAAAAADiUsABszb/AIioaJ6lfifEtGonmp3jmm86rcyZvka/WTTiwb6zWueMvGChG/blhvcpZ5iK7WFGXZ9DDd1XWzZMSuI0aVt8/PnubFKWTJt6mY5zvqT05NFmPJ4FeSfIt06Dc23si7w+71n2i8fXG5UpXB2tUllJmucqfooqXrp6CEsrKOxUsp6YLZpl7Rma0wADpwAAAAAAAAAAAAAAAAAAAAA4bMyXEHndI1Gjzl9Hkk0Rp6JxPk9Gh/Xv3/gzOL8SqqL5cPwWjfqKFTv9irdczeNMe/QqyJ1PGWylNdPO2HFpVZTTT0eud0+zRFcKUKinHOr1Xj7/AHNOVGFOTkorma131/k6VIwnnp6/r0PMc/RvVL2vRFKeVzx23a/tff34k9vWjLnXRrLXv3qZVSpKlN41T6dJdenX+DpGo4NVIp4ejj4PH8/Yj5aZ3x2jZ4W8cy6Zyvo2a06eNe+Cpwi3VSlJLSS2fdbo0ZVIwo89X5VHfPh27mjFi3JnyZP2IpU3jJHG4Se+pTofESm9Kcow/vljGO7S1S+pxX4fJvmk8Z1WNjmXHULaR3HSrjN6zvTco1FJJnhbb8SLx0PTcIqPZl3xs7b8WVZ8KS2jYABvMYAAAAAABwADkAAAAAAAAAAAApcTs/xI6brYugM6np7R8/uLmdKTUmkujf5V4smtJym+bPOu6ax5JPQ1viGxjUzHPLJr5Zaaep8xlTuLOs/zNN4coZw1nqtUZKfg/wDh6GNLNP8Ap/2er4y3nR4+pn2aaknz8vR7vyZp32ZRT7pP1I7Hh7lq1he+xjqW74Tmko6V/iDh8+RVaeHytS+uNdTStranVhGouqw16/dMxuK/GVC0k6cISrSX5lBpRjno5SeM9cFr4f8AiyhcSdCVOVvVxzqnUWOaMv8AlCW0l9DVGFMz1kpcNzg75HyN5xs+6IP/ANAuFC2hKTxD8WCk+iUsxi3/ANnH1Oqk6dRZ11yn4P2y9xmVOpRnCcFUi1iUXqmieKlCar6IXPk019nzf4V/HtYXMatWNSjOXPB5cpuX9kPr8qwfQbbmVvbwl+blWfolgyuEcBsaeJ0qK503jV4Xq/sb8KEpPPvy7EMuVXPjJKMfg9s4pR7F7h88yIVZPGM4XgXLGhy4SI4sdKlw7dppmqjk4RybzGAAAAAAcA5AAAAAAAAAAAAAAAABVvbOM1nqtmeWuOERc+Z7/p5HspMxeJJPLRTlley3HTT0eb4rytabL9jz8ruq1KFLTOmXnTOnkWOK15a46Z+hxwyXNTUkvHT9TyfyN3s9NQlB854zwtzjKhVqKjVjVnNOWkaik3JSjJvDwtMdNCelZ1rmtaQpTlNWsMuolpFJ55IyW+3dn0KrcKaxVpQn26M4jVaXJCMacXrLlWr+rN/+VPjwyL47VbZj0OO1JycZPPLJpd2ljf1PbWlNzgm9NOp5XhvDYSryUdW9ctPCeHls9NTsLmLfNKnOHLpFc0cvpu2V4pd7ddL7cJpJ6NGz4fHkcoYysrKehp2NLCWXkj4fNKCSxgvR2Nc4ZnqMWTI22mR1NyahhMg5tTtGR3fSvXDQTOSKjNMlLSAAAAAAAAAAAAAAAAAAAAOGwDkjqVUiC5u8GPd3jeSu8iksjG6Llzea7lSdVS+XO5j1Lp50Iv655XRGF/I2+mpYdLhV4tw9pvbDKduo01h7eGpv/wBVCaw9e/Yz6tlHLfTp/govGk9yaIttaoUKEan5V5/sa9DhkVHEVv16lW2WEsLBcpXMkm/Q04YldZny1T9FmjYJYWPJaL/JblSK9Gu+vj7+zJ1XRtlpLhke9k9Gil0JKtRIhjVOstTtPhxLbIqtU7qppuRuB1q1VoZm2ttl6SfEX7SRoIzLWWxpIvx+im/ZyACwgAAAAAAAAAAAAADiTwAJPBnXl7jRHPEbtJYRg1a/XJRly+PC7Hj30muK5VrSytP2K9W5I5VNNzG72alOiOFTXUjvKb36e9DrRlr3RZq3GVgq8U10t20+GPTuHnC016ircz3Scox9Hjp5kte3e6WnoV7i9wkmsLyx6/wVptcZZx+jm24zJ5bwsYXXCb3e2vXbsWqnH1BQyn80lGPjpF//AF+hUhYKpBvGNtt9n+7K07NxlTk1nlcWtNF8sU8L/qi1ZKn2RcTXo9Hw3iE5crksabf9n+zNenUy0uz1floYE7uKlDGcR5m/LGr8dfuyex4lmOP+S++38ssnN48bKKwuupHo/wAbEseGTipcJamO7iU1Fr8y/wBNfbJZlRnLGcp9ST+Q6/iRWFL2T1brsdbdOXcltrRLcuwopdDk47vtB3M8RNbxxg0YlKjHUvI3wtIx0+gAEyIAAAAAAAAAAABw2ZHE73GiLd/cYWh5m8rNvUz58nitIuwxt7Ydw3uVa9XoKkiC61MLbZtSRWrVddjq6uUV5bhPTRYRWmWaJreu09DtUk29ytSkW6STCfA0WaMeaL3WPuY93SbeMaJ/z/nU1IVGt9eiXT1ZUvJt/lw2ui217ikmhO0ynGtUhFpJJZa095LfDL3mUVLDw2n0y9Hov7UupT/Cyvninrrh6fTRpvTHQ6c0MJKOFmTzDpp6EFbX2WOUz0de35nHCW+uezWvnp9y1acPhlrBj2FTlikpybeurbxp1z71N3hdXTXppkvhRT6jPflK4y/TtksNIl5WzvGRLDBsWNfRjdv7I6MGtyaMjnlEo4LFOkR8tlm2j1LJHQjhEhavRWwADpwAAAAAAAAAHEng5ILv8oBlX0stmTcLCNCszLvapjyv7NWJd0VKk9cnevFSWSOlHPcju3KOmuDKuLbNP3pFGrRedyenY4jnKZnzrrOr+xdjxCLWNfT+CEePdk68vogemW1jpk0raGmiMrLlJJbZ6mvcVnGP5X5CdCtnSrFLL0X3PM8S4zU5uRQeM6NLCz56di1e0HVTc5yguqjq/pn/AGQU+C06qSj+LBpfLOWcebaK23T4WwlPWLHhSrJ88mst5xJeHZbpJ6PxNDhvwy6bfLOU8a/NjGq6GdCzu6GeePMv7l82Vjd+SPV8Cvspc252FLfjS0MjtLyl7RzbWbiscq9DWtaSxsSTmmS0Im/HhU+jzryuvZLTjgsKJHAlyaUihnL0QpQyyH8XJctF1Htj0iykcgFhAAAAAAAAAAAAAENzHQmI6+zAMC6luYV3U1NXiM8ZPO3FTLPNz13RuwTzZZtmskl6/l3IrTHZefQmu6SaOJfoTf8AM8zVfzF6wi87PyWP0IKzUZaItUrl74M8LT2X29rSNCjaR54trUv3EoJa48ylYz5pLJ34jHOUaK5O0jOlutMqVpxi8x5fo28Iq3N5X/4YeemSOu8LVr1REripjmVObXR/5RjdM1qUegtZ1FHM4eHdEEbdSn8ungVbO7rwxlPD7prxfvwNawxN88cJ9V/BYtW0it7hNmjThhJdi1RRBAt00epKPOpklMiu4t4w/wDaJObQh5iVetEV72c20W5a+hs044RSs6eXkvnca0jlvbAALCAAAAAAAAAAAAAOs1odgAeX4zQayeWuFrsfRuIWynFnhOJ2rUsamD5OPT2jb8e+aILWo8rt72RZvqmIle3io649Trf18oq6oLGt2efvaj5tW/1NjhslJJJPzx5nnrucstL7dTU4RJwwtW37+2SvC1vpdlX68PRUIJa7eJblSUk34GXLLaNS0qdPXsa1KfDG21087eZcsRhzP6aev+zb4dQcFGTWNNe2evUsTpRp5k2v3Mu6vZz0gorxbfTyMvisfv2afN5OL0bkKkZdM+n7kdCxUJuSWFJPTovp2+hj2lRxabb18MY1WyerPR2N0qi2fmTx0ra8vZXacJ69HeGh2lWXchupNJoyf6p7fX2zVdqDPEeRsxq5fkdrSDZmUZvK7+X0Zp2FbleupVORU+ljjxXDdoUsIlI6VRNEhuXoxsAA6AAAAAAAAAAAAAAACOpPBicUpqfQ2qsMlKpanGtnU9Hi7qwqJ6YwZV/Rms5TPoUrQgq2i7FN/Hmi6c7R8thVxLOPN/sXKd9Bap6+/Q9zX4TCW8V6GbX+F6Lz8pUvjaLX8lUeWfxGk8Lp18MavXw/Y2eCfENOo1HH3X6bnNX4LoPOE1nxOth8Iwoz54N58ScxaZGqxtHpK9FTw8LB0p0VHZL33fUs2cGlhvJLUisMXj10rm36KU+XGqj6e8E1tdLONBNxWuER29dZaUUsb9Pe5Q+P2Xe0OJwlpKJmUKHM9Y6+9z0FJ50ZU4hQqLDpxz9Gk/LJO48+nIvx4V6uI4XX31Llvok33/UrqjV5ot0pPzj6vU0rWE2/mhhLbb9mJw92dq+F+yLpWt44LJslaRkYAB04AAAAAAAAAAAAAAADjByADo4HWVFEoAK0rZEM7UvnDQBlztCGVsbDgdJUgDHjTwdbiGhrO3RDWs01jVfQ41s6no8/Bt6Pz9+9iSNL/wBi8Vv3x/s0ocJS2lLzw+uf3H/i3zRfO9OmEU/iLfyHSlSbL8aZ2jQJfwyyY0VutkWDskSKmd1AmcOsESIJHIOAAAAAAAAAAAAAAAAAAAAAAAAAAAA4YABwzhnAAByAAcoAAHKOQAAAAAAAAAAAAAAAAD//2Q=="
                alt="Maca">
        </div>
    </section>
    <section class="work-hours" id="radno-vreme">
        <div class="section-title">
            <h2>Radno vreme</h2>
            <p>Uvek tu kada nam zatrebate</p>
        </div>
        <div class="hours-container">
            <div class="hours-row">
                <span class="day">Ponedeljak - Petak</span>
                <span class="time">08:00 - 20:00</span>
            </div>
            <div class="hours-row">
                <span class="day">Subota</span>
                <span class="time">09:00 - 17:00</span>
            </div>
            <div class="hours-row">
                <span class="day">Nedelja</span>
                <span class="time">10:00 - 14:00</span>
            </div>
            <div class="emergency">
                🚨 Hitne intervencije: 24/7 - Pozovite 012-123-456
            </div>
        </div>
    </section>
    <section class="contact" id="kontakt">
        <div class="section-title">
            <h2>Kontaktirajte nas</h2>
            <p>Imate pitanje? javite nam se!</p>
        </div>
        <div class="contact-wrapper">
            <div class="contact-info">
                <h3>Informacije</h3>
                <p>📍 Ulica: Lenjinova 42,Kula</p>
                <p>📞 011-123-456</p>
                <p>📧 info@vetcare.rs</p>
                <p>🕐 Radnim danima 08-20h</p>
            </div>
            <form class="contact-form" onsubmit="submitForm(event)">
                <input type="text" placeholder="Vase ime" required>
                <input type="email" placeholder="Vas email" required>
                <textarea placeholder="Vasa poruka" required></textarea>
                <button type="submit">Posalji poruku</button>
            </form>
        </div>
    </section>
    <footer>
        <p> 2025 VetCare - Veterinarska Ordinacija. Sva prava zadrana.</p>
    </footer>
    <div class="toast" id="toast">✅ Poruka je uspesbno poslata!</div>

</body>

</html>
