<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CLAN CENT | CLAN CENT</title>
    <link rel="stylesheet" href="style.css">

    <style>
        /* ------ مربع البحث الفخم ------ */
        .search-container {
            position: relative;
            margin-right: 20px;
        }

        .search-input {
            padding: 10px 20px;
            border-radius: 25px;
            border: none;
            outline: none;
            width: 220px;
            font-size: 15px;
            background: #181818;
            color: #fff;
            transition: .3s;
            box-shadow: 0 0 10px #7b2bff80;
        }

        .search-input:focus {
            box-shadow: 0 0 20px #9d55ff;
            width: 260px;
        }

        .search-results {
            position: absolute;
            top: 50px;
            right: 0;
            width: 260px;
            background: #111;
            color: #fff;
            border-radius: 15px;
            box-shadow: 0 0 15px #7b2bff60;
            display: none;
            padding: 10px;
            animation: fade .3s ease-in-out;
        }

        @keyframes fade {
            from { opacity: 0; transform: translateY(-5px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .search-results p {
            margin: 5px 0;
            padding: 8px;
            background: #1a1a1a;
            border-radius: 10px;
            cursor: pointer;
            transition: .2s;
        }

        .search-results p:hover {
            background: #7b2bff;
        }
    </style>

</head>
<body>

<header>
    <div class="logo">
        <a href="#join-us" style="color:red; text-decoration:none; font-weight:bold;">CLAN CENT</a>
    </div>

    <!-- مربع البحث 👇 -->
    <div class="search-container">
        <input type="text" class="search-input" id="searchBox" placeholder="ابحث في الموقع..." oninput="searchSite()">
        <div class="search-results" id="resultsBox"></div>
    </div>
    <!-- نهاية مربع البحث -->

    <nav>
        <a href="#about">عن الكلان</a>
        <a href="#members">الأعضاء</a>
        <a href="#news">الأخبار</a>
        <a href="#contact">تواصل</a>
    </nav>
</header>

<section class="hero">
    <h1>CLAN CENT</h1>
    <p>القوة • الهيبة • الاحتراف</p>
    <a class="btn" href="#members" id="join-us">انضم لنا</a>
</section>

<section id="about" class="section">
    <h2>عن كلان سنت</h2>
    <p>كلان سنت هو كلان محترف، ملتزم بالانضباط والعمل الجماعي، يضم أقوى اللاعبين لتحقيق أعلى الإنجازات.</p>
</section>

<section id="members" class="section">
    <h2>أعضاء الكلان</h2>
    <div class="members-grid">
        <div class="member">
            <div class="avatar">EK</div>
            <h3>WES</h3>
            <p>Leader</p>
        </div>
        <div class="member">
            <div class="avatar">EV</div>
            <h3>MALIK</h3>
            <p>Co-Leader</p>
        </div>
        <div class="member">
            <div class="avatar">EG</div>
            <h3>CENT|GHOST</h3>
            <p>Pro Member</p>
        </div>
    </div>
</section>

<section id="news" class="section">
    <h2>أحدث الأخبار</h2>
    <div class="news-grid">
        <div class="news-item">
            <h3>تحديث جديد للكلان</h3>
            <p>تم إضافة رتب جديدة وتطوير نظام العضوية.</p>
        </div>
        <div class="news-item">
            <h3>مسابقة الأسبوع</h3>
            <p>شارك في التحدي واحصل على لقب العضو المتميز.</p>
        </div>
    </div>
</section>

<section id="contact" class="section contact">
    <h2>تواصل معنا</h2>
    <form>
        <input type="text" placeholder="اسمك" required>
        <input type="email" placeholder="بريدك" required>
        <textarea placeholder="رسالتك" required></textarea>
        <button type="submit">إرسال</button>
    </form>
</section>

<footer>
    <p>© 2025 CLAN CENT — جميع الحقوق محفوظة</p>
</footer>

<script>
    // ------ نظام البحث ------
    function searchSite() {
        let input = document.getElementById("searchBox").value.trim();
        let resultsBox = document.getElementById("resultsBox");

        if (input === "") {
            resultsBox.style.display = "none";
            return;
        }

        let results = [];

        // البحث في الأقسام
        if ("عن".includes(input)) results.push("<p onclick=\"location='#about'\">عن الكلان</p>");
        if ("اعضاء مالك ويس قهوست".includes(input)) results.push("<p onclick=\"location='#members'\">أعضاء الكلان</p>");
        if ("مسابقة اخبار تحديث".includes(input)) results.push("<p onclick=\"location='#news'\">الأخبار</p>");
        if ("تواصل رسالة".includes(input)) results.push("<p onclick=\"location='#contact'\">تواصل معنا</p>");

        // لو ما فيه نتائج
        if (results.length === 0) {
            resultsBox.innerHTML = "<p>لا توجد نتائج…</p>";
        } else {
            resultsBox.innerHTML = results.join("");
        }

        resultsBox.style.display = "block";
    }
</script>

</body>
</html>
body {
    margin: 0;
    font-family: "Tajawal", sans-serif;
    background: #0b0b0b;
    color: #fff;
}

/* ===== الهيدر ===== */
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 40px;
    background: #000000;
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 999;
}

header .logo {
    font-size: 26px;
    font-weight: bold;
    color: #e60000;
}

/* ===== قائمة الروابط ===== */
header nav {
    display: flex;              /* ترتيب الروابط في صف واحد */
    justify-content: flex-end;  /* سحبها لليمين */
    flex-grow: 1;               /* تأخذ المساحة بين اللوقو وبقية الصفحة */
    gap: 25px;                  /* المسافة بين الروابط */
    margin-left: 60px;          /* مسافة بين اللوقو والقائمة */
}

header nav a {
    color: #fff;
    text-decoration: none;
    transition: 0.3s;
}

header nav a:hover {
    color: rgb(230, 0, 0);
}

/* ===== قسم البطل ===== */
.hero {
    min-height: 80vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding-top: 100px;
}

.hero h1 {
    font-size: 60px;
    margin: 0;
}

.hero p {
    font-size: 22px;
    margin: 10px 0 20px;
}

.btn {
    padding: 14px 30px;
    background: #e60000;
    color: #fff;
    text-decoration: none;
    border-radius: 8px;
    font-size: 18px;
    transition: 0.3s;
}

.btn:hover {
    background: #ff1a1a;
}

/* ===== الأقسام ===== */
.section {
    padding: 80px 40px;
    text-align: center;
}

/* ===== شبكة الأعضاء ===== */
.members-grid, .gallery-grid, .news-grid {
    display: grid;
    gap: 20px;
    margin-top: 30px;
}

.members-grid {
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}

.member {
    background: #1a1a1a;
    padding: 20px;
    border-radius: 10px;
    transition: 0.3s;
}

.member:hover {
    background: #e60000;
    color: #fff;
}

.avatar {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    background: #e60000;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: bold;
    font-size: 24px;
    margin: 0 auto 10px;
}

/* ===== معرض الصور ===== */
.gallery-grid {
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
}

.media-item {
    background: #1a1a1a;
    padding: 50px;
    border-radius: 10px;
    font-size: 18px;
}

/* ===== الأخبار ===== */
.news-grid {
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
}

.news-item {
    background: #1a1a1a;
    padding: 20px;
    border-radius: 10px;
    transition: 0.3s;
}

.news-item:hover {
    background: #e60000;
    color: #fff;
}

/* ===== التواصل ===== */
.contact input, .contact textarea {
    width: 80%;
    padding: 12px;
    margin: 10px 0;
    border: none;
    border-radius: 8px;
    background: #1a1a1a;
    color: #fff;
}

.contact button {
    padding: 12px 30px;
    background: #e60000;
    color: #fff;
    border: none;
    border-radius: 8px;
    font-size: 18px;
    transition: 0.3s;
}

.contact button:hover {
    background: #ff1a1a;
}

/* ===== الفوتر ===== */
footer {
    text-align: center;
    padding: 20px;
    background: #111;
    margin-top: 40px;
}

/* ===== تعديل اللوقو ===== */
.logo a {
    color: red;
    text-decoration: none;
    font-weight: bold;
}
// نموذج معالجة الفورم
document.querySelector("form")?.addEventListener("submit", e => {
    e.preventDefault();
    alert("تم إرسال رسالتك بنجاح!");
});
