<!DOCTYPE html>
<html lang="ur">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>اردو شاعری </title>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Nastaliq+Urdu:wght@400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* --- Keyframes for Animation --- */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(15px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* --- Base Styles - Modern & Refined --- */
        body {
            font-family: 'Noto Nastaliq Urdu', 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            line-height: 1.8;
            direction: rtl;
            text-align: right;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            min-height: 100vh;
            transition: background-color 0.5s ease, color 0.5s ease;
            overflow-x: hidden;
            padding-top: 40px;
            padding-bottom: 40px;
            box-sizing: border-box;
        }

        .container {
            max-width: 700px;
            width: 95%;
            padding: 30px;
            border-radius: 20px;
            text-align: center;
            transition: background-color 0.5s ease, box-shadow 0.5s ease;
            position: relative;
            z-index: 1;
            box-sizing: border-box;
            display: flex;
            flex-direction: column;
        }

        h1 {
            margin-bottom: 30px;
            font-size: 2.6em;
            padding-bottom: 15px;
            font-weight: 700;
            border-bottom: 3px solid;
            transition: color 0.5s ease, border-image 0.5s ease;
        }

        /* --- Category Buttons - Refined --- */
        .category-buttons {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 35px;
        }

        .category-button {
            padding: 12px 28px;
            border: 2px solid transparent;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1.1em;
            font-weight: 500;
            transition: all 0.3s ease;
            white-space: nowrap;
        }

        .category-button:hover {
            transform: translateY(-4px);
        }

        /* --- Shayari List Container --- */
        .shayari-list-container {
            max-height: 65vh;
            overflow-y: auto;
            padding: 5px;
            margin-bottom: 25px;
            transition: background-color 0.5s ease, box-shadow 0.5s ease;
            -ms-overflow-style: none;
            scrollbar-width: none;
        }
        .shayari-list-container::-webkit-scrollbar { display: none; }

        /* --- Individual Shayari Card - Redesigned --- */
        .individual-shayari-card {
            position: relative; /* For number positioning */
            padding: 30px;
            padding-right: 50px; /* Space for the number */
            margin-bottom: 20px;
            border-radius: 16px;
            transition: all 0.3s ease;
            text-align: center;
            animation: fadeIn 0.5s ease-out forwards;
        }

        .individual-shayari-card:hover {
            transform: scale(1.02);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        /* --- Poem Numbering Style --- */
        .shayari-number {
            position: absolute;
            top: 20px;
            right: 15px;
            width: 35px;
            height: 35px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1em;
            font-weight: 700;
            transition: background-color 0.3s, color 0.3s;
        }

        .individual-shayari-card p {
            font-size: 1.5em;
            margin-bottom: 20px;
            color: inherit;
            line-height: 2.0;
            white-space: pre-wrap;
            font-weight: 500;
        }

        /* --- Shayari Card Actions - Sleek Design --- */
        .shayari-card-actions {
            display: flex;
            justify-content: center;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
            margin-top: 15px;
        }

        .action-button {
            background-color: transparent;
            border: 2px solid;
            padding: 10px 22px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1em;
            font-weight: 500;
            transition: all 0.25s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .action-button:hover {
            transform: translateY(-2px);
        }

        .action-button i { font-size: 1.1em; }

        .action-button.favorite.favorited {
            background-color: #e74c3c !important;
            color: white !important;
            border-color: #e74c3c !important;
            box-shadow: 0 4px 12px rgba(231, 76, 60, 0.3);
        }

        /* Ad Placeholder - Subtle Design */
        .ad-placeholder {
            width: 100%;
            min-height: 80px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1em;
            text-align: center;
            margin: 20px 0;
            border-radius: 12px;
            padding: 10px;
            transition: background-color 0.5s ease, border-color 0.5s ease, color 0.5s ease;
            box-sizing: border-box;
            border: 2px dashed;
            animation: fadeIn 0.5s ease-out forwards;
        }

        /* Footer - Refined */
        .footer {
            margin-top: auto;
            padding-top: 20px;
            font-size: 0.9em;
            transition: color 0.5s ease, border-color 0.5s ease;
            border-top: 1px solid;
            opacity: 0.7;
        }

        /* --- Side Menu & Toggle --- */
        .menu-toggle-button {
            position: fixed;
            top: 25px;
            left: 25px;
            border: none;
            font-size: 1.8em;
            cursor: pointer;
            transition: all 0.3s ease;
            z-index: 101;
            width: 55px;
            height: 55px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .menu-toggle-button:hover { transform: scale(1.1) rotate(15deg); }

        .side-menu {
            height: 100%; width: 0; position: fixed;
            z-index: 102; top: 0; left: 0;
            overflow-x: hidden; transition: 0.4s ease-in-out;
            padding-top: 80px; box-shadow: 5px 0 25px rgba(0,0,0,0.3);
            box-sizing: border-box;
        }
        .side-menu ul { list-style: none; padding: 0; margin: 0; }
        .side-menu ul li {
            padding: 22px 40px; font-size: 1.3em; color: inherit;
            display: flex; align-items: center; gap: 18px;
            transition: 0.3s all ease; cursor: pointer;
            border-bottom: 1px solid; text-align: right;
        }
        .side-menu ul li:hover { padding-right: 50px; }
        .side-menu .close-btn {
            position: absolute; top: 25px; left: 30px; font-size: 3em;
            color: inherit; cursor: pointer; transition: transform 0.3s ease, color 0.3s ease;
        }
        .side-menu .close-btn:hover { transform: rotate(180deg); color: #e74c3c; }
        .menu-overlay {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-color: rgba(0, 0, 0, 0.65);
            opacity: 0; visibility: hidden;
            transition: opacity 0.4s ease, visibility 0.4s ease;
            z-index: 100;
        }
        .menu-overlay.active { opacity: 1; visibility: visible; }

        /* --- Add Shayari Form --- */
        .add-shayari-form {
            display: none; flex-direction: column; gap: 20px;
            padding: 35px; border-radius: 18px; margin-top: 25px;
        }
        .add-shayari-form h2 { font-size: 2.2em; margin-bottom: 15px; }
        .add-shayari-form textarea,
        .add-shayari-form select {
            width: 100%; padding: 18px; border-radius: 12px;
            border: 2px solid; font-family: 'Noto Nastaliq Urdu', 'Arial', sans-serif;
            font-size: 1.2em; resize: vertical; min-height: 180px;
            box-sizing: border-box; transition: all 0.3s ease;
        }
        .add-shayari-form select { min-height: auto; cursor: pointer; }
        .add-shayari-form textarea:focus,
        .add-shayari-form select:focus { outline: none; }
        
        .add-shayari-form .form-buttons { display: flex; gap: 15px; margin-top: 15px; }
        .add-shayari-form button {
            flex-grow: 1; padding: 16px 25px; border: none;
            border-radius: 50px; cursor: pointer; font-size: 1.2em;
            font-weight: 600; transition: all 0.25s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        .add-shayari-form button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.18);
        }

        /* --- Dark Theme --- */
        body.dark-theme { background-color: #121212; color: #e0e0e0; }
        .dark-theme .container { background: #1e1e1e; box-shadow: 0 10px 50px rgba(0, 0, 0, 0.5); }
        .dark-theme h1 { color: #bb86fc; border-image: linear-gradient(to left, #bb86fc, #9b59b6) 1; }
        .dark-theme .category-button { background-color: #333; color: #e0e0e0; border-color: #444; box-shadow: 0 4px 10px rgba(0,0,0,0.3); }
        .dark-theme .category-button:hover { background-color: #444; border-color: #bb86fc; color: #bb86fc; }
        .dark-theme .category-button.active { background-color: #bb86fc; color: #121212; border-color: #bb86fc; box-shadow: 0 5px 20px rgba(187, 134, 252, 0.3); }
        .dark-theme .shayari-list-container { background: #121212; }
        .dark-theme .individual-shayari-card { background-color: #2a2a2a; box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3); }
        .dark-theme .individual-shayari-card:hover { box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4); }
        .dark-theme .shayari-number { background-color: #333; color: #bb86fc; }
        .dark-theme .action-button { border-color: #bb86fc; color: #bb86fc; }
        .dark-theme .action-button:hover { background-color: rgba(187, 134, 252, 0.15); }
        .dark-theme .ad-placeholder { background-color: #2a2a2a; border-color: #444; color: #aaa; }
        .dark-theme .footer { color: #888; border-top-color: #333; }
        .dark-theme .side-menu { background-color: #1e1e1e; color: #e0e0e0; }
        .dark-theme .side-menu ul li { border-color: #333; }
        .dark-theme .side-menu ul li:hover { background-color: rgba(255, 255, 255, 0.05); }
        .dark-theme .menu-toggle-button { background-color: #333; color: #e0e0e0; }
        .dark-theme .add-shayari-form { background-color: #2a2a2a; }
        .dark-theme .add-shayari-form h2 { color: #bb86fc; }
        .dark-theme .add-shayari-form textarea, .dark-theme .add-shayari-form select { background-color: #333; border-color: #555; color: #e0e0e0; }
        .dark-theme .add-shayari-form textarea:focus, .dark-theme .add-shayari-form select:focus { border-color: #bb86fc; box-shadow: 0 0 0 3px rgba(187, 134, 252, 0.25); }
        .dark-theme .add-shayari-form button#submit-new-shayari { background: linear-gradient(45deg, #bb86fc, #9b59b6); color: #121212; }
        .dark-theme .add-shayari-form button#cancel-add-shayari { background-color: #4f4f4f; color: #ccc; }

        /* --- Light Theme - Modernized --- */
        body.light-theme { background: linear-gradient(to bottom, #f7f9fc, #eef2f7); color: #2c3e50; }
        .light-theme .container { background: #ffffff; box-shadow: 0 10px 50px rgba(0, 0, 0, 0.08); }
        .light-theme h1 { color: #2980b9; border-image: linear-gradient(to left, #3498db, #2980b9) 1; }
        .light-theme .category-button { background-color: #ffffff; color: #555; border: 2px solid #e0e6ed; }
        .light-theme .category-button:hover { border-color: #3498db; color: #3498db; }
        .light-theme .category-button.active { background-color: #3498db; color: white; border-color: #3498db; box-shadow: 0 5px 20px rgba(52, 152, 219, 0.3); }
        .light-theme .shayari-list-container { background: #f0f4f8; }
        .light-theme .individual-shayari-card { background-color: #ffffff; box-shadow: 0 8px 25px rgba(0, 0, 0, 0.07); }
        .light-theme .shayari-number { background-color: #eef2f7; color: #3498db; }
        .light-theme .action-button { border-color: #3498db; color: #3498db; }
        .light-theme .action-button:hover { background-color: rgba(52, 152, 219, 0.1); }
        .light-theme .ad-placeholder { background-color: #eef2f7; border-color: #d1d9e6; color: #8a9cb1; }
        .light-theme .footer { color: #8a9cb1; border-top-color: #e0e6ed; }
        .light-theme .side-menu { background-color: #ffffff; color: #2c3e50; }
        .light-theme .side-menu ul li { border-color: #e0e6ed; }
        .light-theme .side-menu ul li:hover { background-color: #f7f9fc; }
        .light-theme .menu-toggle-button { background-color: #fff; color: #2c3e50; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }
        .light-theme .add-shayari-form { background-color: #f8f9fa; }
        .light-theme .add-shayari-form h2 { color: #2980b9; }
        .light-theme .add-shayari-form textarea, .light-theme .add-shayari-form select { background-color: #fff; border-color: #ced4da; color: #495057; }
        .light-theme .add-shayari-form textarea:focus, .light-theme .add-shayari-form select:focus { border-color: #3498db; box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.2); }
        .light-theme .add-shayari-form button#submit-new-shayari { background: linear-gradient(45deg, #3498db, #2980b9); color: white; }
        .light-theme .add-shayari-form button#cancel-add-shayari { background-color: #e9ecef; color: #495057; }
    </style>
</head>
<body class="dark-theme">

    <div id="sideMenu" class="side-menu">
        <a href="javascript:void(0)" class="close-btn" onclick="closeNav()">&times;</a>
        <ul>
            <li onclick="showFavorites()"><i class="fas fa-heart"></i>پسندیدہ شاعری</li>
            <li onclick="toggleTheme()"><i class="fas fa-palette"></i>تھیم تبدیل کریں</li>
            <li onclick="showAddShayariForm()"><i class="fas fa-plus-circle"></i>شاعری شامل کریں</li>
        </ul>
    </div>
    <div id="menuOverlay" class="menu-overlay" onclick="closeNav()"></div>

    <button class="menu-toggle-button" onclick="openNav()"><i class="fas fa-bars"></i></button>

    <div class="container" id="main-content">
        <h1>اردو شاعری ایپ</h1>
        
        <div class="category-buttons">
            <button class="category-button active" data-category="muhabbat">محبت</button>
            <button class="category-button" data-category="jaun_elia">جون ایلیا</button>
            <button class="category-button" data-category="ahmad_faraz">احمد فراز</button>
            <button class="category-button" data-category="allama_iqbal">علامہ اقبال</button>
            <button class="category-button" data-category="gham">غم</button>
            <button class="category-button" data-category="dosti">دوستی</button>
            <button class="category-button" data-category="funny">مزاحیہ</button>
            <button class="category-button" data-category="udas">اداس</button>
            <button class="category-button" data-category="behtareen">بہترین</button>
            <button class="category-button" data-category="mir_taqi_mir">میر تقی میر</button>
            <button class="category-button" data-category="khubsurat">خوبصورت</button>
            <button class="category-button" data-category="nafrat">نفرت</button>
            <button class="category-button" data-category="qismat">قسمت</button>
            <button class="category-button" data-category="khamoshi">خاموشی</button>
        </div>

        <div id="shayari-view">
            <div class="shayari-list-container" id="shayari-list-container">
                <!-- Shayari cards will be inserted here by JavaScript -->
            </div>
            <div class="ad-placeholder" id="bottom-ad-slot">
                آپ کا اشتہار یہاں نظر آئے گا
            </div>
        </div>

        <div id="add-shayari-view" class="add-shayari-form">
            <h2>نئی شاعری شامل کریں</h2>
            <textarea id="new-shayari-text" placeholder="یہاں اپنی شاعری لکھیں... (ہر نئی سطر کے لیے انٹر دبائیں)"></textarea>
            <select id="new-shayari-category">
                <option value="muhabbat">محبت</option>
                <option value="funny">مزاحیہ</option>
                <option value="dosti">دوستی</option>
                <option value="gham">غم</option>
                <option value="nafrat">نفرت</option>
                <option value="qismat">قسمت</option>
                <option value="khamoshi">خاموشی</option>
                <option value="udas">اداس</option>
                <option value="behtareen">بہترین</option>
                <option value="khubsurat">خوبصورت</option>
                <option value="allama_iqbal">علامہ اقبال</option>
                <option value="ahmad_faraz">احمد فراز</option>
                <option value="mir_taqi_mir">میر تقی میر</option>
                <option value="jaun_elia">جون ایلیا</option>
            </select>
            <div class="form-buttons">
                <button id="submit-new-shayari">شاعری جمع کروائیں</button>
                <button id="cancel-add-shayari">واپس جائیں</button>
            </div>
        </div>
        
        <div class="footer">
            <p>تمام حقوق محفوظ ہیں © 2025</p>
        </div>
    </div>

<script>
// --- Shayari Data (Greatly Expanded) ---
const defaultShayaris = {
    muhabbat: [ "تمہارے شہر کا موسم بڑا سہانا لگے\nمیں ایک شام چرا لوں اگر برا نہ لگے", "دل کی دھڑکنوں میں بس گیا ہے نام تیرا\nاب تو ہر سانس میں شامل ہے کلام تیرا", "محبت ہے کہ نفرت، کوئی اتنا تو سمجھائے\nکبھی میں دل سے لڑتا ہوں کبھی دل مجھ سے لڑتا ہے", "تیری آنکھوں میں وہ گہرائی ہے\nجو سمندر میں بھی نہیں ملتی", "اک لائن میں کیا تعریف کروں اس کی\nپانی بھی جو دیکھے اسے تو پیاسا ہو جائے", "عشق کی آگ میں جل کر دیکھو کبھی\nیہ وہ شعلہ ہے جو بجھتا نہیں", "تمہاری یادوں کے سائے میں جینا سیکھ لیا\nاب تو تنہائی بھی محفل سی لگتی ہے", "ہر نظر میں تیری صورت نظر آئے\nدل کہتا ہے تو ہی میری منزل ہے", "محبت ایسی ہے کہ بیان نہ کر سکوں\nبس اتنا جان لو تم ہی زندگی ہو", "تمہیں سوچا تو ہر سوچ مہک اٹھی\nتمہیں چاہا تو ہر چاہت خاص ہو گئی", "میری ہر دعا میں شامل ہے نام تیرا\nرب سے مانگا ہے تو بس تجھے ہی مانگا ہے", "اب تو ہر خواب تیرا ہے، ہر خیال تیرا\nیہ دل دیوانہ صرف تیرا ہے", "محبت کا سفر ہے یہ، کبھی ختم نہ ہوگا\nہم ساتھ چلیں گے جب تک سانسیں ہیں", "تیرے بغیر میری ہر بات ادھوری ہے\nجیسے چاند کے بغیر رات ادھوری ہے", "محبت میں ہم نے خود کو کھو دیا\nاور اس کھونے میں ہی خود کو پا لیا", "جب سے تم آئے زندگی میں بہار آ گئی\nویران دل میں خوشیوں کی قطار آ گئی", "تیری مسکان میری دنیا ہے\nتیری خوشی میری زندگی ہے", "محبت امر ہے، یہ کبھی نہیں مرتی\nیہ تو روحوں کا رشتہ ہے جو سدا رہتا ہے", "ہماری کہانی یوں ہی لکھتے رہنا\nزمانے کو ہماری محبت یاد رہے", "تیرے لیے جیوں، تیرے لیے مروں\nیہی میری محبت ہے، یہی میری قسم ہے", "دل میں کسی کے راہ کیے جا رہا ہوں میں\nکتنا حسین گناہ کیے جا رہا ہوں میں", "وہ پاس رہے یا دور، نظروں میں سمایا رہتا ہے\nایسا پیارا ہے وہ کہ ہر پل یاد آتا ہے", "تم حقیقت نہیں ہو حسرت ہو\nجو ملے خواب میں وہ دولت ہو", "کیا کہیں کتنی ہی باتیں تھیں جو کہنا تھیں\nاس کو دیکھا تو ہمیں لفظ ہی یاد نہ آئے", "تیرے عشق کی انتہا چاہتا ہوں\nمیری سادگی دیکھ میں کیا چاہتا ہوں", "یہ محبت بھی ایک نیکی ہے\nآؤ دریا میں ڈال آتے ہیں", "کیسے کہہ دوں کہ مجھے چھوڑ دیا ہے اس نے\nبات تو سچ ہے مگر بات ہے رسوائی کی", "اس کی یاد آئی ہے سانسو ذرا آہستہ چلو\nدھڑکنوں سے بھی عبادت میں خلل پڑتا ہے", "وہ میرے سینے سے لگ کر کسی اور کے لیے روئے\nاے خدا یہ کیسا انصاف ہے تیرا", "چلو اچھا ہوا کام آ گئی دیوانگی اپنی\nورنہ ہم زمانے بھر کو سمجھانے کہاں جاتے", "تم محبت بھی موسم کی طرح نبھاتے ہو\nکبھی برستے ہو، کبھی ایک بوند کو ترساتے ہو", "زندگی میں تو سبھی پیار کیا کرتے ہیں\nمیں تو مر کر بھی میری جان تجھے چاہوں گا", "دل کے رشتے بھی عجیب ہوتے ہیں\nدور رہ کر بھی قریب ہوتے ہیں", "کون کہتا ہے کہ محبت برباد کرتی ہے\nنبھانے والا مل جائے تو دنیا یاد کرتی ہے", "سنو! مجھے ہر پل تمہاری یاد آتی ہے\nکبھی سانسوں کے چلنے پر، کبھی دل کے مچلنے پر", "وہ شخص ایک چھوٹی سی بات پر یوں روٹھ کر چل دیا\nجیسے اسے صدیوں سے کسی بہانے کی تلاش تھی", "لوگ صورت پہ مرتے ہیں جناب\nمجھے تو اس کی آواز سے بھی عشق ہے", "تمہارے نام کے حروف کتنے خوبصورت ہیں\nمیں ہر روز انہیں اپنی انگلیوں سے لکھتا ہوں", "یہ ضروری تو نہیں کہ تم مل جاؤ\nمگر تمہیں سوچنا بھی محبت سے کم نہیں", "ہم نے سینے سے لگایا دل نہ اپنا بن سکا\nمسکرا کر تم نے دیکھا، دل تمہارا ہو گیا", "عشق وہ کھیل نہیں جو چھوٹے دل والے کھیلیں\nروح تک کانپ جاتی ہے، صدقے اگر سچے ہوں", "کبھی آؤ میرے روبرو، تمہیں اپنے دل کا حال سناؤں\nکیسے دھڑکتا ہے یہ دل تیرے نام کے ساتھ", "محبت دو لوگوں کے بیچ کا نشہ ہے\nجسے پہلے ہوش آ جائے وہ بے وفا ہے", "میں نے ہر بار تجھ سے ملتے وقت\nتجھ سے ملنے کی آرزو کی ہے", "اک نظر دیکھ لے مجھے اے جانِ تمنا\nمیری ہر حسرت تیرے دیدار کی محتاج ہے", "تمہارے ساتھ خاموشی بھی باتیں کرتی ہے\nتم نہ ہو تو محفلیں بھی ویران لگتی ہیں", "بس اک شخص میرے دل کی ضد ہے\nنہ اس جیسا کوئی چاہیے، نہ اس کے سوا کوئی", "یہ عشق نہیں آساں بس اتنا سمجھ لیجیے\nاک آگ کا دریا ہے اور ڈوب کے جانا ہے", "کتنی خوبصورت ہو جاتی ہے دنیا\nجب کوئی کہتا ہے تم یاد آ رہے ہو", "دل بھی توڑا تو سلیقے سے نہ توڑا تم نے\nبے وفائی کے بھی آداب ہوا کرتے ہیں" ],
    funny: [ "عشق میں ہم نے کچھ ایسا کیا\nدیواروں کو ہی محبوب بنا لیا", "بیوی سے کیا ڈرنا، وہ تو فرشتہ ہے\nبس اس کے پروں سے ڈر لگتا ہے، جو اڑتی پھرتی ہے", "میں نے کہا: چاند دیکھنا ہے\nاس نے کہا: میرے کچن میں دیکھ لو، روٹی جل رہی ہے", "رات کو میں نے موبائل چارج پر لگایا\nسویرا ہوا تو پتا چلا چارجر ہی نہیں تھا", "استاد: 'لوہا گرم کر کے ٹھنڈا کرو، کیا بنے گا؟'\nشاگرد: 'روٹی!'", "جب سے دیکھا ہے تیرا قد لمبا\nمیں نے اپنی سوچ کی اونچائی بڑھا لی", "آج کل کی محبتیں بھی عجیب ہیں\nپروفائل تصویر اچھی ہو تو بات شروع ہوتی ہے", "میری بیوی کو سونا بہت پسند ہے\nآدھا دن بستر پر اور آدھا دن دکانوں میں", "ایک مچھر نے میرے کان میں گانا گایا\nمیں نے چپل اٹھا کر اسے پائلٹ بنا دیا", "کاش محبت میں بھی حساب ہوتا\nایک دیتا، ایک لیتا، حساب برابر ہوتا", "پیار کرنے کی حد ہوتی ہے\nلیکن میری بیگم کی غصے کی کوئی حد نہیں", "میں نے زندگی سے پوچھا تو اتنی مشکل کیوں ہے؟\nزندگی نے ہنس کر کہا کیونکہ تم پاکستانی ہو!", "انٹرنیٹ پیکج ختم ہونے پر دل یوں روتا ہے\nجیسے کسی بے گناہ کو پھانسی ہو جائے", "دانا کتنا بھی ہو دانا\nفٹبال کو ہمیشہ گول ہی سمجھے گا", "آج کل کی لڑکیاں پریشان رہتی ہیں کہ\n'اب کون سا نیا فلٹر استعمال کریں!'", "میں نے عشق میں سب کچھ کھو دیا\nپھر بھی ایک عدد موٹیویشنل اسپیکر بن گیا", "آج کے بعد کسی کو دل کا حال نہیں سناؤں گا\nکیونکہ سب کو ہنسی آتی ہے", "دل جلا کر روشنی کرنے والے\nیہ بھی بتا دو، بلب کا کیا قصور تھا؟", "ٹوٹے ہوئے دل کو جوڑنا آسان نہیں\nکیونکہ اس میں چپس بھر جاتی ہے", "محبت کی پہلی منزل ہے ڈرامہ\nدوسری منزل ہے دھوکہ، اور آخری منزل ہے فیس بک بلاک", "محبت اندھی ہوتی ہے\nلیکن پڑوسی اندھے نہیں ہوتے", "وہ مجھے کہتی ہے کہ تم میرے لیے کچھ بھی کر سکتے ہو؟\nمیں نے کہا ہاں، سوائے سبزی لانے کے", "اتنی سردی ہے کہ دل کرتا ہے\nرضائی میں ہی دفتر کھول لوں", "شادی وہ طوفان ہے جس کا سامنا\nہر مرد کو کرنا پڑتا ہے", "میں اس کی گلی میں جاتا رہا، وہ چھت پر آتی رہی\nنہ اس نے کچھ کہا، نہ میں نے، قصہ ختم، پیسہ ہضم", "وہ کہتی تھی تمہارے بغیر مر جاؤں گی\nآج کل بخار بھی نہیں آتا اسے", "محبت اور نوکری میں کوئی فرق نہیں\nانسان کرتا بھی رہے گا اور روتا بھی رہے گا", "گرمی میں دل کرتا ہے کہ فریج میں بیٹھ جاؤں\nمگر امی کی چپل یاد آ جاتی ہے", "عقل بادام کھانے سے نہیں\nدھوکے کھانے سے آتی ہے", "ڈاکٹر نے کہا روزانہ پانچ کلومیٹر چلو\nدو سال ہو گئے، کابل پہنچ گیا ہوں", "اس نے کہا تمہاری آنکھوں میں ڈوب جاؤں\nمیں نے کہا پہلے سوئمنگ سیکھ لو", "وہ جو کہتے تھے کہ بچھڑیں گے نہ ہم کبھی\nآج کل سگنل پر ہارن بجا کر آگے نکل جاتے ہیں", "ہر کامیاب مرد کے پیچھے عورت کا ہاتھ ہوتا ہے\nاور ناکام مرد کے پیچھے دو تین کا", "محبت ایک ایسا جنگل ہے\nجہاں خوبصورت ہرنوں کو خطرناک شیر کھا جاتے ہیں", "پہلے لوگ بیل کی طرح کام کرتے تھے\nاب لوگ بیل ہیں، جو کام ہی نہیں کرتے", "کچھ لڑکیاں اتنی خوبصورت ہوتی ہیں کہ\nلڑکے خود ہی بھائی بول دیتے ہیں", "زندگی میں ٹینشن ہی ٹینشن ہے\nپھر بھی ان لبوں پر مسکان ہے", "کچھ لوگوں کی باتیں سن کر\nدل کرتا ہے انہیں چاند پر چھوڑ آئیں", "وہ آئیں ہمارے گھر میں، خدا کی قدرت ہے\nکبھی ہم ان کو، کبھی اپنے گھر کو دیکھتے ہیں", "اگر آپ کسی کو چھوٹا سمجھتے ہیں\nتو دور سے دیکھ رہے ہیں، قریب جا کر دیکھیں", "امتحان میں سوال وہ آتے ہیں\nجو ہم نے چھوڑے ہوتے ہیں", "وہ ہمیں دیکھ کر مسکرائے\nہم انہیں دیکھ کر گھبرائے", "پہلے محبت ہوئی، پھر شادی\nپھر نہ محبت رہی، نہ شادی", "آج کل کے بچے بھی کمال کرتے ہیں\nدودھ نہیں پیتے، سگریٹ پیتے ہیں", "کچھ لوگ چپل کی طرح ہوتے ہیں\nساتھ بھی چلتے ہیں اور پیچھے سے کیچڑ بھی اچھالتے ہیں", "میں نے دل سے کہا اسے بھول جا\nدل نے کہا، تم دماغ سے کام لو", "وہ کہتے ہیں کہ ہم آپ کے دل میں رہتے ہیں\nہم نے کہا، ٹھیک ہے، کرایہ دیتے رہنا", "دنیا میں سب سے مشکل کام\nاپنے کام سے کام رکھنا ہے", "کچھ لوگ اتنے کنجوس ہوتے ہیں کہ\nمیسج بھی مسڈ کال کی طرح کرتے ہیں", "اگر زندگی میں سکون چاہتے ہو\nتو لوگوں کی باتوں کو دل پر لینا چھوڑ دو" ],
    dosti: [ "دوستی وہ رشتہ ہے جو خون کا نہیں ہوتا\nلیکن خون کے رشتوں سے بڑھ کر ہوتا ہے", "دوست بن کر ایسا نبھایا تو نے\nکہ دشمن بھی دیکھ کر جلتے ہیں", "دوستی میں کوئی شرط نہیں ہوتی\nبس سچا دل اور خلوص ہوتا ہے", "ہر قدم پر ساتھ نبھانے والے دوست\nقسمت والوں کو ہی ملتے ہیں", "دوستی کا رشتہ سب سے حسین ہے\nاس میں نہ کوئی امید نہ کوئی شکایت", "سچی دوستی نصیب والوں کو ملتی ہے\nاور ہم وہ نصیب والے ہیں", "دوست ہو تو ایسا، جو ہر غم میں ساتھ دے\nخوشی میں تو ساری دنیا ساتھ ہوتی ہے", "یہ دوستی ہم نہیں توڑیں گے کبھی\nیہ وعدہ ہے ہمارا، یہ قسم ہے ہماری", "دوستوں کے بغیر زندگی ادھوری ہے\nجیسے پھولوں کے بغیر باغ ادھورا ہے", "تیرے جیسا یار کہاں، ایسا یارانہ کہاں\nیاد کرے گی دنیا تیرا میرا افسانہ", "دوستی میں خود کو بھلا دینا ہی دوستی ہے\nدوست کے لیے جینا ہی اصل زندگی ہے", "ہر مشکل میں ساتھ کھڑے رہنے والے دوست\nخدا کا انمول تحفہ ہوتے ہیں", "دوستی کا کوئی مول نہیں ہوتا\nیہ تو دلوں کا سودا ہے", "دوست وہ ہے جو تیرے دکھ میں شریک ہو\nاور تیری خوشی میں تجھ سے زیادہ خوش ہو", "یہ دوستی تا قیامت رہے گی\nیہ رشتہ کبھی پرانا نہیں ہوگا", "دوست کی ہر بات مان لینا ہی دوستی ہے\nچاہے وہ بات غلط ہی کیوں نہ ہو", "اچھے دوست قسمت سے ملتے ہیں\nاور برے دوست سبق دے جاتے ہیں", "دشمن لاکھ ہوں، دوستوں کی کمی نہیں\nجب تک دوست ساتھ ہیں، کوئی غم نہیں", "دوستوں سے بڑھ کر کوئی اور نہیں ہوتا\nیہ وہ خزانہ ہیں جو کبھی ختم نہیں ہوتا", "دوستی کا مقام سب سے اعلیٰ ہے\nاس رشتے میں کوئی غرور نہیں ہوتا", "ایک سچا دوست ہزار رشتہ داروں سے بہتر ہے\nجو مشکل وقت میں آپ کا ساتھ نہ چھوڑے", "دوستی وہ نہیں جو جان دیتی ہے\nدوستی وہ ہے جو مسکان دیتی ہے", "کرنا ہے اگر دوستی تو مثال بن کر کرو\nکہ لوگ کہیں، کاش میرا بھی کوئی ایسا دوست ہوتا", "دوست وہ آئینہ ہے جو تمہیں تمہاری حقیقت دکھائے\nاور تمہاری غلطیوں پر پردہ بھی ڈالے", "وقت اور دوست دو ایسی چیزیں ہیں\nجو ایک بار کھو جائیں تو دوبارہ نہیں ملتیں", "کچھ دوست زندگی میں ایسے ملتے ہیں\nجو خاندان کا حصہ بن جاتے ہیں", "دوستی کا بھرم صرف وہی رکھ سکتے ہیں\nجن کے وجود میں سمندر جتنا دل ہو", "لوگ کہتے ہیں زمین پر فرشتہ نہیں ملتا\nشاید انہوں نے کوئی اچھا دوست نہیں دیکھا", "دوست وہ ہے جو آپ کی خاموشی کو بھی سمجھ لے\nاور آپ کے الفاظ کے پیچھے چھپے درد کو بھی", "کتنے خوبصورت ہوتے ہیں وہ رشتے\nجن پر کوئی حق بھی نہ ہو اور شک بھی نہ ہو", "دوستی میں دوری کوئی معنی نہیں رکھتی\nاگر دلوں میں محبت سچی ہو", "سچا دوست وہ ہے جو تب بھی آپ کے ساتھ ہو\nجب ساری دنیا آپ کے خلاف ہو", "رکھو حوصلہ، وہ منظر بھی آئے گا\nجب دوست کہے گا، چل چائے پینے چلتے ہیں", "دوستوں کی محفل میں بیٹھ کر دیکھو\nزندگی کے سارے غم بھول جاؤ گے", "وہ دوست ہی کیا جو مصیبت میں کام نہ آئے\nاور وہ مصیبت ہی کیا جس میں دوست یاد نہ آئے", "دوست کا غصہ بھی نعمت ہے\nکیونکہ وہ آپ کی بھلائی کے لیے ہوتا ہے", "کچھ دوستوں کے ساتھ صرف وقت نہیں\nبلکہ زندگی گزر جاتی ہے", "دوستی ایک ایسا پھول ہے جو کبھی مرجھاتا نہیں\nاسے بس خلوص کے پانی کی ضرورت ہوتی ہے", "ہزاروں دوست بنانے سے بہتر ہے\nایک ایسا دوست بناؤ جو ہزاروں کے خلاف تمہارا ساتھ دے", "دوستی کا مطلب صرف ساتھ رہنا نہیں\nبلکہ دور رہ کر بھی ایک دوسرے کو یاد رکھنا ہے", "دوست وہ ہے جو آپ کو آپ سے بہتر جانتا ہے\nاور پھر بھی آپ سے محبت کرتا ہے", "زندگی میں کچھ دوست ٹام اینڈ جیری کی طرح ہوتے ہیں\nلڑتے بھی ہیں اور ایک دوسرے کے بغیر رہ بھی نہیں سکتے", "دوست کی غلطی ریت پر لکھو تاکہ ہوا اسے مٹا دے\nاور اس کا احسان پتھر پر لکھو تاکہ کوئی اسے مٹا نہ سکے", "ہماری دوستی کی عمر ہم سے بھی زیادہ ہوگی\nتمہاری ہر خوشی، ہر غم پر ہمارا حق ہوگا", "جب کوئی نہ ہو ساتھ تو دوست یاد آتے ہیں\nجب ہر طرف ہو اندھیرا تو دوست چراغ جلاتے ہیں", "دوستی میں نہ کوئی دن، نہ کوئی رات ہوتی ہے\nیہ تو احساس کی بات ہے، جو دل سے ہوتی ہے", "دوست وہ ہے جو تمہاری کامیابی پر فخر کرے\nاور تمہاری ناکامی پر تمہارا حوصلہ بڑھائے", "دوستوں سے بچھڑ کر یہ حقیقت کھلی\nکہ دنیا میں کوئی بھی چیز مستقل نہیں", "اے دوست، تیری دوستی پر ناز ہے مجھے\nہر پل، ہر لمحہ تیرا ساتھ ہے مجھے", "دوستی وہ نہیں جو مطلب سے کی جائے\nدوستی تو وہ ہے جو دل سے نبھائی جائے" ],
    gham: [ "غمِ حیات میں ہم نے بہت کچھ کھو دیا\nجو پایا تھا وہ بھی گنوا دیا", "زندگی کا ہر لمحہ غمگین ہے\nخوشی تو بس ایک خواب ہے", "غم کی چادر اوڑھ کر سو گئے ہم\nشاید خوابوں میں ہی سکون مل جائے", "اشکوں کی بارش تھمتی نہیں ہے\nدل کا موسم ہمیشہ برسات کا رہتا ہے", "ہر خوشی کے بعد غم ضرور آتا ہے\nجیسے دن کے بعد رات آتی ہے", "تنہائیوں میں غم ہی ساتھی ہے\nجب کوئی اپنا نہیں ہوتا", "دل کا درد کوئی سمجھ نہ پایا\nسب نے کہا، یہ تو شاعر ہے", "غموں کا بوجھ اب اٹھایا نہیں جاتا\nاے زندگی، اب تو رحم کر", "رونے کو جی چاہتا ہے ہر پل\nمگر آنسو بھی اب سوکھ گئے ہیں", "اداس ہے دل، اداس ہیں ہم\nیہ دنیا بھی اداس لگتی ہے", "اس دنیا میں بس غم ہی غم ہیں\nخوشیاں تو بس مہمان ہوتی ہیں", "آنکھوں میں آنسو، لب پر خاموشی\nیہ ہے میری زندگی کی کہانی", "غموں نے میرا گھر بنا لیا ہے\nاب خوشی کا کوئی راستہ نہیں", "اب خوشی کی کوئی امید نہیں\nجب امید ہی ٹوٹ جائے تو کیا کریں", "ہر رات غم کی کہانی سناتی ہے\nچاندنی بھی اب اداس لگتی ہے", "دل کا یہ عالم ہے کہ بیان نہ کر سکوں\nبس اتنا جان لو کہ زندہ ہوں", "غموں سے پیچھا چھڑانا مشکل ہے\nیہ تو سائے کی طرح ساتھ چلتے ہیں", "زندگی نے ہر موڑ پر غم دیا\nاب تو مسکرانا بھی بھول گئے ہیں", "اب ہنسنا بھول گئے ہم\nجب ہنسنے کی کوئی وجہ ہی نہیں", "غموں کا سمندر پار کرنا مشکل ہے\nاور کوئی کنارہ بھی نظر نہیں آتا", "توڑ کر جوڑ لو چاہے ہر چیز دنیا کی\nسب کچھ قابلِ مرمت ہے، اعتبار کے سوا", "وہ روئے تو بہت پر مجھ سے منہ موڑ کر روئے\nکوئی مجبوری ہوگی جو دل توڑ کر روئے", "ہم تو سمجھے تھے کہ اک زخم ہے بھر جائے گا\nکیا خبر تھی کہ رگِ جاں میں اتر جائے گا", "عمر بھر لکھتے رہے پھر بھی ورق سادہ رہا\nجانے کیا لفظ تھے جو ہم سے تحریر نہ ہوئے", "اکیلے ہیں تو کیا ہوا، یہ زندگی بھی گزر جائے گی\nہم اپنی تنہائی میں بھی بادشاہوں کی طرح رہتے ہیں", "اب اداس پھرتے ہو سردیوں کی شاموں میں\nاس طرح تو ہوتا ہے اس طرح کے کاموں میں", "کچھ زخم انسان کو اندر سے کھا جاتے ہیں\nاور لوگ سمجھتے ہیں کہ وہ بدل گیا ہے", "وقت کے ایک تماشے نے ہمیں کیا کچھ نہ سکھایا\nاپنوں کی محفل میں غیروں کا کردار نبھایا", "موت نے آنکھیں ملائیں تھیں کئی بار مجھ سے\nتیرا چہرہ سامنے آیا تو میں مر نہ سکا", "جن کے آنگن میں امیری کا شجر لگتا ہے\nان کا ہر عیب بھی زمانے کو ہنر لگتا ہے", "کوئی نہیں کرتا یاد جب تک میں نہ کروں یاد\nیہاں مطلب پرستوں کی بستی ہے، صاحب", "کتنی جلدی یہ ملاقات گزر جاتی ہے\nپیاس بجھتی نہیں کہ برسات گزر جاتی ہے", "ہم نے کاٹی ہیں تیری یاد میں راتیں اکثر\nدل سے جب بھی تیری یادوں کے بادل گزرے", "اب کے بچھڑے تو شاید کبھی خوابوں میں ملیں\nجس طرح سوکھے ہوئے پھول کتابوں میں ملیں", "کوئی امید بر نہیں آتی\nکوئی صورت نظر نہیں آتی", "وہ جو گیت تم نے سنا نہیں، میری عمر بھر کا ریاض تھا\nمیرے درد کی تھی وہ داستاں، جسے تم ہنسی میں اڑا گئے", "دل سے نکلے ہیں جو لفظ\nاثر رکھتے ہیں، پر نہیں رکھتے", "ہم تو فنا ہو گئے اس کی آنکھیں دیکھ کر\nنہ جانے وہ آئینہ کیسے دیکھتے ہوں گے", "زندگی یوں بھی گزر ہی جاتی\nکیوں تیرا راہگزر یاد آیا", "ضبط لازم ہے مگر دکھ ہے قیامت کا\nظالم اب کے بھی نہ روئے گا تو مر جائے گا", "وہ لوگ بہت خوش قسمت تھے\nجو عشق کو کام سمجھتے تھے یا کام سے عاشقی کرتے تھے", "اب تو اس راہ سے وہ شخص گزرتا بھی نہیں\nاب کس امید پہ دروازے سے جھانکیں ہم", "بچھڑتے وقت اس نے کہا تھا\nنہ سوال کرنا، نہ جواب ملے گا", "رونے والے تو ہزاروں ملیں گے تمہیں\nکوئی ہنسانے والا ملے تو مجھے یاد کرنا", "کچھ اس طرح سے نظر انداز ہو گئے\nجیسے اضافی حرف تھے تیری زندگی کی کتاب میں", "وہ شخص جو کہتا تھا کہ تو نہ ملا تو مر جاؤں گا\nوہ آج بھی زندہ ہے یہی بات کسی اور سے کہنے کے لیے", "ہم تو جی رہے تھے ان کا نام لے کر\nوہ گزرتے تھے ہمارا سلام لے کر", "ایک مدت سے تیری یاد بھی آئی نہ ہمیں\nاور ہم بھول گئے ہوں تجھے، ایسا بھی نہیں", "یہ دکھ نہیں کہ اندھیروں سے صلح کی ہم نے\nملال یہ ہے کہ اب صبح کی طلب بھی نہیں", "اتنا بھی نہ روٹھو کہ منانے والا ہی مر جائے\nپھر کس سے کہو گے کہ اب مان جاؤ" ],
    nafrat: [ "نفرت کا زہر ہر رشتے کو ختم کر دیتا ہے\nمحبت تو بس ایک دھوکا ہے", "اب دل میں نفرت کے سوا کچھ نہیں\nمحبت کا باب ہمیشہ کے لیے بند کر دیا", "جس سے محبت تھی، اب اس سے نفرت ہے\nیہ بھی محبت کی ایک قسم ہے", "نفرت کی آگ نے سب کچھ جلا دیا\nاب تو راکھ کے سوا کچھ نہیں بچا", "نفرت انسان کو تنہا کر دیتی ہے\nاور میں اپنی تنہائی میں خوش ہوں", "میں اب نفرت کے قابل بھی نہیں\nاتنی حقارت سے دیکھا اس نے مجھے", "نفرت کا کوئی ٹھکانہ نہیں ہوتا\nیہ تو بس دلوں میں پلتی رہتی ہے", "دل میں اب کوئی محبت نہیں\nصرف نفرت کی حکومت ہے", "نفرت کی وجہ سے دنیا ویران ہے\nہر طرف بس نفرت کے شعلے ہیں", "اب ہر چہرے سے نفرت ہوتی ہے\nجب سے اس کا اصلی چہرہ دیکھا ہے", "نفرت کا راستہ بہت تاریک ہے\nاور میں اس راستے کا مسافر ہوں", "کسی سے اتنی نفرت بھی نہ کرنا\nکہ وہ تمہارے خوابوں میں بھی آنے لگے", "نفرت دل کو پتھر بنا دیتی ہے\nاور میرا دل اب پتھر کا ہے", "میں نفرت میں بھی اکلوتا ہوں\nکوئی میری طرح نفرت نہیں کر سکتا", "ہر شخص سے اب نفرت ہونے لگی ہے\nجب سے تم سے محبت کی ہے", "نفرت کا انجام ہمیشہ برا ہوتا ہے\nمگر شروع تو محبت سے ہی ہوتا ہے", "نفرت کی ہر حد پار کر دی\nاب واپسی کا کوئی راستہ نہیں", "اب محبت کا کوئی نام نہیں\nصرف نفرت کی داستان ہے", "نفرت نے میری زندگی چھین لی\nاب تو بس سانسیں چل رہی ہیں", "نفرت کی دیواریں بہت اونچی ہیں\nانہیں گرانا اب ممکن نہیں", "تم سے بچھڑ کر یہ احساس ہوا\nکہ نفرت بھی محبت کا ہی ایک روپ ہے", "اب تو نفرت بھی نہیں رہی تم سے\nتم اب اس قابل بھی نہیں رہے", "دل میں نفرت ہو تو انسان کچھ بھی کر سکتا ہے\nمحبت میں تو بس رو سکتا ہے", "میں نے نفرت کو بھی محبت سے پالا ہے\nتاکہ وہ بھی بے وفا نہ نکلے", "تیری یادیں بھی اب زہر لگتی ہیں\nنفرت کی آگ میں جلتی ہیں", "وہ جو کہتے تھے کہ تم بن جی نہیں سکتے\nآج نفرت سے منہ پھیر لیتے ہیں", "محبت کا انجام اگر نفرت ہے\nتو ایسی محبت سے توبہ", "نفرت کی ایک خاصیت ہے\nیہ کبھی دھوکا نہیں دیتی", "اب تو آئینے سے بھی ڈر لگتا ہے\nکہیں اس میں بھی تیرا عکس نہ نظر آئے", "تیری بے وفائی نے مجھے نفرت کرنا سکھا دیا\nورنہ میں تو محبت کا पुजारी تھا", "نفرت کی تلوار بہت تیز ہوتی ہے\nیہ رشتوں کو پل بھر میں کاٹ دیتی ہے", "اب تو تیرا نام سن کر بھی غصہ آتا ہے\nکبھی اسی نام سے دن شروع ہوتا تھا", "نفرت کرنے والوں کے دل میں بھی\nکبھی محبت کا دیا جلتا تھا", "میں نے اپنی نفرت کو اتنا بلند کر لیا ہے\nکہ اب محبت کی آواز سنائی نہیں دیتی", "وہ شخص اب میرے لیے مر چکا ہے\nجس کے لیے میں کبھی جیتا تھا", "نفرت کی دنیا میں خوش آمدید\nیہاں کوئی دھوکا نہیں دیتا", "اگر نفرت کرنا گناہ ہے\nتو میں گناہ گار ہی سہی", "اب تو خوابوں میں بھی نفرت ہے\nنیندیں بھی اب دشمن ہو گئی ہیں", "تیری صورت اب آنکھوں میں چبھتی ہے\nکبھی اسی صورت پر مرتے تھے", "نفرت کا سفر بہت لمبا ہے\nاور میں تھکنا نہیں چاہتا", "جس دل میں تم رہتے تھے\nاب وہاں نفرت کا راج ہے", "تم نے مجھے نفرت کرنا سکھایا\nاب میں تمہیں اس کا ہنر دکھاؤں گا", "نفرت کی آندھی میں سب کچھ اڑ گیا\nمحبت کا گھروندہ بھی نہ بچا", "میں نے نفرت کو اپنا مذہب بنا لیا ہے\nاب کوئی اور عقیدہ قبول نہیں", "وہ جو محبت کے دعوے کرتے تھے\nآج نفرت کی مثال بن گئے ہیں", "نفرت کی آگ میں جلنا بھی ایک فن ہے\nہر کوئی اس میں جل نہیں سکتا", "اب تو تیری خوشی سے بھی نفرت ہے\nدعا ہے کہ تو ہمیشہ اداس رہے", "میں نے نفرت کا بیج بویا ہے\nاب فصل کاٹنے کا انتظار ہے", "تیری ہر یاد کو مٹا دوں گا\nنفرت کی ایسی داستان لکھوں گا", "اب تو بس ایک ہی خواہش ہے\nکہ تجھے بھی مجھ سے نفرت ہو جائے" ],
    qismat: [ "قسمت میں جو لکھا ہے، وہ ہو کر رہے گا\nچاہے تم کتنا بھی تدبیر کر لو", "قسمت کا کھیل بھی کتنا عجیب ہوتا ہے\nجسے چاہتے ہیں وہ ملتا نہیں", "کبھی قسمت سے لڑنا بھی ضروری ہے\nشاید وہ بھی بدلنے کا انتظار کر رہی ہو", "قسمت کے فیصلے بدل بھی سکتے ہیں\nاگر دعاؤں میں اثر ہو", "ہر انسان اپنی قسمت خود لکھتا ہے\nیہ تو بس کہنے کی باتیں ہیں", "قسمت بھی ان کا ساتھ دیتی ہے\nجو خود کچھ کرنے کا حوصلہ رکھتے ہیں", "میری قسمت میں تو بس غم لکھے تھے\nخوشیاں تو بس خوابوں میں ملیں", "قسمت نے ایسا کھیل کھیلا\nکہ ہم اپنے ہی گھر میں مہمان ہو گئے", "جو قسمت میں نہیں ہوتا\nوہ دعاؤں سے بھی نہیں ملتا", "قسمت سے زیادہ اور وقت سے پہلے\nنہ کسی کو کچھ ملا ہے نہ ملے گا", "کبھی کبھی قسمت بھی حیران ہو جاتی ہے\nجب انسان ہار نہیں مانتا", "میری قسمت مجھ سے روٹھ گئی\nجب سے تم مجھ سے روٹھے ہو", "قسمت کی لکیروں پر یقین نہ کر\nتقدیر تو ان کی بھی ہوتی ہے جن کے ہاتھ نہیں ہوتے", "سب کچھ قسمت پر چھوڑ دینا\nبھی ایک طرح کی بزدلی ہے", "کبھی کبھی قسمت بھی مہربان ہوتی ہے\nجب انسان بالکل ٹوٹ جاتا ہے", "میری قسمت میں تو بس انتظار لکھا ہے\nکبھی تیرا، کبھی موت کا", "قسمت بھی بادشاہی اسی کو دیتی ہے\nجس میں غلامی کرنے کا حوصلہ ہو", "کوشش اتنی کرو کہ قسمت بھی بول اٹھے\nلے لے بیٹا، یہ تو تیرا حق ہے", "قسمت میں لکھا ٹل نہیں سکتا\nیہ سوچ کر ہم نے جینا سیکھ لیا", "کبھی قسمت پر رونا آتا ہے\nکبھی اپنی حماقتوں پر", "وہ ملا تو صدیوں بعد بھی جیسے اپنا تھا\nوہ بچھڑا تو جیسے کبھی ملا ہی نہ تھا، سب قسمت کا کھیل ہے", "ہم تو قسمت سے بھی لڑ جاتے\nاگر تم ہمارے ساتھ ہوتے", "قسمت کی کتاب کا ہر ورق\nخدا نے خود لکھا ہے", "کبھی کبھی قسمت بھی امتحان لیتی ہے\nاور ہم اسے بدقسمتی سمجھ بیٹھتے ہیں", "میری قسمت میں شاید تم نہیں تھے\nورنہ محبت تو ہم نے بھی سچی کی تھی", "قسمت کو दोष کیا دینا\nجب خواب ہی اونچے دیکھے تھے", "قسمت سے لڑنے کا مزہ ہی کچھ اور ہے\nیہ ہار بھی جائے تو جیت لگتی ہے", "کبھی کبھی قسمت ہمیں وہاں لے جاتی ہے\nجہاں جانے کا ہم نے کبھی سوچا بھی نہیں ہوتا", "میری قسمت میں تو بس سفر لکھا ہے\nمنزل کا کوئی نشان نہیں", "قسمت کا لکھا کون ٹال سکتا ہے\nہم تو بس کٹھ پتلیاں ہیں", "کبھی کبھی قسمت بھی مہربان ہو کر\nایسے لوگوں سے ملوا دیتی ہے جو زندگی بدل دیتے ہیں", "میری قسمت میں تو بس آنسو تھے\nمسکراہٹیں تو بس ادھار کی تھیں", "قسمت بھی انہی کو آزماتی ہے\nجو ہر آزمائش پر پورا اتر سکتے ہیں", "کبھی کبھی قسمت پر بھروسہ کر لینا چاہیے\nشاید وہ ہمارے لیے کچھ بہتر سوچ رہی ہو", "میری قسمت میں تو بس تنہائی لکھی ہے\nمحفلیں تو بس خوابوں میں سجتی ہیں", "قسمت بھی کیا چیز ہے\nکبھی راجہ کو رنک بنا دیتی ہے، کبھی رنک کو راجہ", "کبھی کبھی قسمت بھی ہمیں وہ دے دیتی ہے\nجس کی ہم نے کبھی تمنا بھی نہیں کی ہوتی", "میری قسمت میں تو بس جلنا لکھا ہے\nچاہے چراغ بن کر یا دل بن کر", "قسمت سے شکایت کیسی\nجب سب کچھ اسی کا دیا ہوا ہے", "کبھی کبھی قسمت بھی ساتھ چھوڑ دیتی ہے\nجب انسان کو سب سے زیادہ ضرورت ہوتی ہے", "میری قسمت میں تو بس انتظار ہے\nاور انتظار کا پھل میٹھا ہوتا ہے", "قسمت کا ستارہ جب بلند ہوتا ہے\nتو دشمن بھی دوست بن جاتے ہیں", "کبھی کبھی قسمت بھی ہمیں وہیں لا کر کھڑا کر دیتی ہے\nجہاں سے ہم بھاگنا چاہتے ہیں", "میری قسمت میں تو بس ہار لکھی تھی\nجیت تو بس ایک خواب تھا", "قسمت بھی ان کا ساتھ دیتی ہے\nجن کے ارادے مضبوط ہوں", "کبھی کبھی قسمت بھی ہمیں وہ سکھا دیتی ہے\nجو کوئی استاد نہیں سکھا سکتا", "میری قسمت میں تو بس درد لکھا تھا\nدوا تو بس ایک بہانہ تھی", "قسمت کا سکندر وہی کہلاتا ہے\nجو ہر حال میں خوش رہنا جانتا ہے", "کبھی کبھی قسمت بھی ہمیں ان سے ملا دیتی ہے\nجن سے ہمیں کبھی نہیں ملنا چاہیے تھا", "میری قسمت میں تو بس خاموشی لکھی ہے\nالفاظ تو بس دل بہلانے کے لیے ہیں" ],
    khamoshi: [ "خاموشی بہت کچھ کہہ جاتی ہے\nکان نہیں، دل لگا کر سنو", "دل کی خاموشی بھی ایک زبان ہے\nجو ہر کوئی سمجھ نہیں سکتا", "خاموش رہنا کبھی کبھی بہتر ہوتا ہے\nجواب دینے سے رشتے ٹوٹ جاتے ہیں", "تیری خاموشی نے مجھے مار ڈالا\nکچھ تو کہہ دیتے، ہم جی لیتے", "اس کی خاموشی میں بھی ایک ادا تھی\nجو ہم سمجھ نہ سکے", "خاموشی ایک عظیم نعمت ہے\nاگر تم اسے سمجھ سکو", "جب الفاظ ختم ہو جائیں\nتو خاموشی شروع ہوتی ہے", "میری خاموشی کو میری کمزوری نہ سمجھنا\nمیں نے بس صبر کرنا سیکھ لیا ہے", "کبھی کبھی خاموشی بھی چیختی ہے\nمگر سننے والا کوئی نہیں ہوتا", "خاموشی سے بڑا کوئی جواب نہیں\nاور معافی سے بڑا کوئی انتقام نہیں", "بہت شور ہے میرے اندر\nمگر باہر سے میں خاموش ہوں", "اس کی خاموشی بتا رہی تھی\nکہ وہ اب میرا نہیں رہا", "خاموشی اختیار کر لی ہے میں نے\nاب باتیں دل سے ہوتی ہیں", "کبھی کبھی خاموشی ہی سب سے خوبصورت جواب ہوتی ہے\nخاص کر جب سوال بے معنی ہو", "جو لوگ زیادہ خاموش رہتے ہیں\nان کے اندر طوفان چھپے ہوتے ہیں", "میری خاموشی کو سمجھنے کی کوشش کرو\nمیرے الفاظ تو سبھی سمجھتے ہیں", "خاموشی ایک ایسی عبادت ہے\nجس میں کوئی ریاکاری نہیں ہوتی", "اس نے میری خاموشی کو میرا غرور سمجھا\nاور میں اس کی خوشی کے لیے خاموش تھا", "کبھی کبھی خاموش رہنا ہی بہتر ہے\nکیونکہ کچھ باتوں کا کوئی جواب نہیں ہوتا", "میری خاموشی میں بھی ہزاروں باتیں ہیں\nکاش کوئی سمجھنے والا ہوتا", "خاموشی ایک ایسا پردہ ہے\nجس کے پیچھے ہزاروں راز چھپے ہوتے ہیں", "جب انسان اندر سے ٹوٹ جاتا ہے\nتو باہر سے خاموش ہو جاتا ہے", "اس کی خاموشی نے سب کچھ کہہ دیا\nجو وہ کبھی کہہ نہ سکا", "خاموشی ایک ایسی طاقت ہے\nجو ہر کسی کے پاس نہیں ہوتی", "میں خاموش ہوں، مگر بے خبر نہیں\nسب کچھ دیکھ رہا ہوں", "اس کی خاموشی بھی ایک سازش تھی\nجسے ہم سمجھ نہ پائے", "خاموشی سے بہتر کوئی دوست نہیں\nیہ کبھی دھوکا نہیں دیتی", "میری خاموشی کو میری رضا نہ سمجھنا\nشاید میں کسی طوفان کی تیاری کر رہا ہوں", "کبھی کبھی خاموشی بھی بہت کچھ بتا دیتی ہے\nاگر سننے والے کے پاس دل ہو", "اس کی خاموشی میں ایک عجیب سی کشش تھی\nجو مجھے اس کی طرف کھینچتی تھی", "خاموشی ایک ایسا سمندر ہے\nجس کی گہرائی کوئی نہیں ناپ سکتا", "میں نے خاموشی سے بھی باتیں کی ہیں\nجب کوئی سننے والا نہیں تھا", "اس کی خاموشی نے میرے دل پر\nایسا زخم لگایا جو کبھی نہیں بھرے گا", "خاموشی ایک ایسی زبان ہے\nجسے صرف احساس والے لوگ سمجھ سکتے ہیں", "میں خاموش رہ کر بھی بہت کچھ کہہ جاتا ہوں\nکاش تم سمجھ پاتے", "اس کی خاموشی ایک پہیلی تھی\nجسے میں سلجھا نہ سکا", "خاموشی ایک ایسی دعا ہے\nجو سیدھی خدا تک پہنچتی ہے", "میری خاموشی کو میری ہار نہ سمجھنا\nیہ تو میری جیت کی پہلی سیڑھی ہے", "کبھی کبھی خاموشی بھی ایک جواب ہوتی ہے\nجو بہت کچھ کہہ جاتی ہے", "اس کی خاموشی نے مجھے سکھایا\nکہ ہر بات کا جواب دینا ضروری نہیں", "خاموشی ایک ایسا ہتھیار ہے\nجو بغیر خون بہائے دشمن کو شکست دے سکتا ہے", "میں خاموش ہوں کیونکہ میرے پاس الفاظ نہیں\nاپنے درد کو بیان کرنے کے لیے", "اس کی خاموشی ایک طوفان کا پیش خیمہ تھی\nاور ہم اسے سکون سمجھ بیٹھے", "خاموشی ایک ایسا راز ہے\nجو ہر کسی پر آشکار نہیں ہوتا", "میں نے اپنی خاموشی میں پناہ لی ہے\nدنیا کے شور سے بچنے کے لیے", "اس کی خاموشی نے مجھے بتایا\nکہ وہ اب مجھ سے بہت دور جا چکا ہے", "خاموشی ایک ایسی عبادت ہے\nجس کا اجر صرف خدا دیتا ہے", "میری خاموشی کو میری بے حسی نہ سمجھنا\nمیں نے بس اپنے جذبات پر قابو پا لیا ہے", "کبھی کبھی خاموشی بھی ایک سزا ہوتی ہے\nجو انسان کو اندر سے توڑ دیتی ہے", "اس کی خاموشی نے میرے دل میں\nایسی آگ لگائی جو کبھی نہیں بجھے گی" ],
    udas: [ "اداسی نے مجھے گھیر لیا ہے\nاب تو مسکرانا بھی بھول گیا ہوں", "آج دل کچھ اداس اداس سا ہے\nشاید کسی کی یاد آ رہی ہے", "یہ اداس شام اور تیری یاد\nدونوں مل کر مجھے مار ڈالیں گے", "اداس رہنا بھی ایک فن ہے\nہر کوئی اس فن کا ماہر نہیں ہوتا", "تیری جدائی میں یہ دل اداس ہے\nکاش تو واپس آ جائے", "اداسی میرے چہرے پر لکھی ہے\nپڑھنے والا کوئی نہیں", "آج پھر دل اداس ہے\nشاید آج پھر کوئی اپنا یاد آیا ہے", "یہ اداس موسم اور میری تنہائی\nدونوں مل کر مجھے رلاتے ہیں", "اداس لوگوں کی مسکراہٹ\nسب سے خوبصورت ہوتی ہے", "تیری کمی نے مجھے اداس کر دیا\nورنہ میں تو بہت خوش مزاج تھا", "اداسی ایک ایسی بیماری ہے\nجس کا کوئی علاج نہیں", "آج کل میں خود سے بھی اداس ہوں\nنہ جانے کیوں", "یہ اداس راتیں اور میری سوچیں\nدونوں مجھے سونے نہیں دیتیں", "اداس ہونا میری عادت نہیں\nمگر کیا کروں، حالات مجبور کر دیتے ہیں", "تیری یادیں مجھے اداس کر دیتی ہیں\nکاش میں تجھے بھول پاتا", "اداسی جب حد سے بڑھ جائے\nتو انسان خاموش ہو جاتا ہے", "آج موسم بھی اداس ہے\nشاید وہ بھی کسی کو یاد کر رہا ہے", "یہ اداس آنکھیں اور یہ ٹوٹا دل\nیہ ہے میری محبت کی نشانی", "اداس لوگوں کو سمجھنا\nہر کسی کے بس کی بات نہیں", "تیری خوشی کے لیے میں اداس ہوں\nشاید میری اداسی تجھے خوش کر دے", "اداسی ایک ایسی دوست ہے\nجو کبھی ساتھ نہیں چھوڑتی", "آج پھر شام اداس ہے\nشاید سورج بھی کسی سے روٹھا ہے", "یہ اداس غزلیں اور میرے آنسو\nیہ ہے میری زندگی کا خلاصہ", "اداس رہنا مجھے اچھا نہیں لگتا\nمگر خوش رہنے کی کوئی وجہ نہیں", "تیری باتیں مجھے اداس کر دیتی ہیں\nکاش تو خاموش ہی رہتا", "اداسی ایک ایسی بادل ہے\nجو بن برسے ہی چلا جاتا ہے", "آج میں اتنا اداس ہوں\nکہ رونے کو بھی جی نہیں چاہتا", "یہ اداس گلیاں اور میرے قدم\nنہ جانے کس منزل کی تلاش میں ہیں", "اداس لوگوں کی کہانیاں\nاکثر ادھوری رہ جاتی ہیں", "تیری تصویر دیکھ کر اداس ہو جاتا ہوں\nکاش تو حقیقت میں میرے پاس ہوتا", "اداسی ایک ایسا زہر ہے\nجو انسان کو آہستہ آہستہ مارتا ہے", "آج ہوا بھی اداس ہے\nشاید وہ بھی کسی کے لیے رو رہی ہے", "یہ اداس چاند اور میرے خواب\nدونوں ادھورے ہیں", "اداس رہنا میری فطرت نہیں\nمگر کیا کروں، تو نے مجھے ایسا بنا دیا", "تیری خاموشی مجھے اداس کر دیتی ہے\nکچھ تو کہہ، چاہے جھوٹ ہی سہی", "اداسی ایک ایسا سمندر ہے\nجس میں ڈوب کر بھی سکون نہیں ملتا", "آج میں خود سے بھی زیادہ اداس ہوں\nشاید آج میں نے خود کو کھو دیا ہے", "یہ اداس پھول اور میری امیدیں\nدونو مرجھا گئے ہیں", "اداس لوگوں کی دعا\nبہت جلد قبول ہوتی ہے", "تیرے شہر سے گزر کر اداس ہو جاتا ہوں\nکاش میں اس شہر میں کبھی آیا ہی نہ ہوتا", "اداسی ایک ایسی سزا ہے\nجو بے گناہ کو بھی ملتی ہے", "آج بارش بھی اداس ہے\nشاید وہ بھی کسی کے غم میں رو رہی ہے", "یہ اداس نظمیں اور میرے جذبات\nیہ ہے میری محبت کی داستان", "اداس رہنا اب میری پہچان بن گیا ہے\nلوگ مجھے اسی نام سے جانتے ہیں", "تیرے خط پڑھ کر اداس ہو جاتا ہوں\nکاش میں نے انہیں جلایا ہوتا", "اداسی ایک ایسا سایہ ہے\nجو دھوپ میں بھی ساتھ نہیں چھوڑتا", "آج میں بہت اداس ہوں\nشاید آج میری زندگی کا آخری دن ہے", "یہ اداس منظر اور میری آنکھیں\nدونوں تیری راہ تک رہی ہیں", "اداس لوگوں کے پاس\nیادوں کے سوا کچھ نہیں ہوتا", "تیرے بغیر ہر لمحہ اداس ہے\nکاش تو سمجھ پاتا" ],
    behtareen: [ "بہترین انسان وہ ہے جو دوسروں کا بھلا سوچے۔\nاپنا بھلا تو جانور بھی سوچتے ہیں", "بہترین وقت وہی ہے جو دوستوں کے ساتھ گزرے۔\nباقی تو بس عمر گزرتی ہے", "بہترین لمحہ وہ ہے جب تم میرے ساتھ ہو۔\nباقی سب تو بس خواب ہے", "بہترین شاعری وہ ہے جو دل کو چھو لے۔\nالفاظ تو کتابوں میں بھی مل جاتے ہیں", "بہترین فیصلہ وہ ہے جو وقت پر کیا جائے۔\nبعد میں تو بس پچھتاوا ہوتا ہے", "بہترین बदला انتقام خاموشی ہے\nچیخنے سے تو بس گلا خراب ہوتا ہے", "بہترین سبق وہ ہے جو زندگی سکھاتی ہے\nکتابوں سے تو بس علم ملتا ہے", "بہترین دوست وہ ہے جو مشکل میں کام آئے\nخوشی میں تو سبھی ساتھ ہوتے ہیں", "بہترین رشتہ وہ ہے جس میں کوئی شرط نہ ہو\nبس بے لوث محبت ہو", "بہترین تحفہ وقت ہے\nجو ایک بار چلا جائے تو واپس نہیں آتا", "بہترین عمل وہ ہے جو نیکی کی نیت سے کیا جائے\nدکھاوے سے تو بس گناہ ملتا ہے", "بہترین صبر وہ ہے جو غم میں کیا جائے\nخوشی میں تو سبھی صبر کر لیتے ہیں", "بہترین دعا وہ ہے جو دوسروں کے لیے کی جائے\nاپنے لیے تو سبھی مانگتے ہیں", "بہترین زندگی وہ ہے جو سادگی سے گزاری جائے\nشان و شوکت تو بس دکھاوا ہے", "بہترین موت وہ ہے جو شہادت کی ہو\nبستر پر تو سبھی مرتے ہیں", "بہترین علم وہ ہے جو عمل میں لایا جائے\nورنہ تو وہ بس بوجھ ہے", "بہترین انسان وہ ہے جو اپنی غلطی مان لے\nاکڑ تو مردے کی پہچان ہے", "بہترین معافی وہ ہے جو بدلہ لینے کی طاقت ہوتے ہوئے دی جائے\nکمزوری میں تو سبھی معاف کر دیتے ہیں", "بہترین کلام وہ ہے جو مختصر اور جامع ہو\nلمبی باتوں سے تو بس وقت ضائع ہوتا ہے", "بہترین لباس تقویٰ کا ہے\nقیمتی کپڑوں سے تو بس جسم ڈھکتا ہے", "بہترین دولت قناعت ہے\nلالچ تو انسان کو کبھی امیر نہیں ہونے دیتا", "بہترین حسن اخلاق ہے\nصورت تو عمر کے ساتھ ڈھل جاتی ہے", "بہترین طاقت برداشت ہے\nغصہ تو کمزوری کی علامت ہے", "بہترین ساتھی کتاب ہے\nیہ کبھی دھوکا نہیں دیتی", "بہترین عبادت خدمت خلق ہے\nنماز روزے تو صرف اپنے لیے ہیں", "بہترین جہاد اپنے نفس کے خلاف ہے\nدشمن سے تو سبھی لڑتے ہیں", "بہترین گھر وہ ہے جس میں سکون ہو\nمحلوں میں تو بس سازشیں ہوتی ہیں", "بہترین نیند وہ ہے جو محنت کے بعد آئے\nفکروں میں تو بس کروٹیں بدلی جاتی ہیں", "بہترین مسکراہٹ وہ ہے جو آنکھوں سے جھلکے\nہونٹوں سے تو بس دکھاوا ہوتا ہے", "بہترین آنسو وہ ہیں جو خدا کے خوف سے بہیں\nدنیا کے لیے تو سبھی روتے ہیں", "بہترین کامیابی وہ ہے جو محنت سے حاصل ہو\nدھوکے سے تو بس جیت ہوتی ہے، کامیابی نہیں", "بہترین استاد تجربہ ہے\nیہ وہ سبق سکھاتا ہے جو کوئی نہیں سکھا سکتا", "بہترین انتقام یہ ہے کہ تم خود کو بہتر بنا لو\nتاکہ وہ تمہیں دیکھ کر پچھتائیں", "بہترین شخص وہ ہے جو اپنی زبان پر قابو رکھے\nتلوار کا زخم بھر جاتا ہے، زبان کا نہیں", "بہترین دل وہ ہے جس میں کینہ نہ ہو\nصاف دل میں خدا بستا ہے", "بہترین نظر وہ ہے جو عیب نہیں، خوبی دیکھے\nعیب تو ہر کسی میں ہوتے ہیں", "بہترین سوچ وہ ہے جو مثبت ہو\nمنفی سوچ تو انسان کو اندر سے کھا جاتی ہے", "بہترین عادت مطالعہ ہے\nیہ انسان کو کبھی تنہا نہیں ہونے دیتی", "بہترین کام وہ ہے جو خلوص نیت سے کیا جائے\nچاہے وہ کتنا ہی چھوٹا کیوں نہ ہو", "بہترین راز وہ ہے جو سینے میں دفن رہے\nزبان پر آ کر تو وہ تماشا بن جاتا ہے", "بہترین زندگی وہ ہے جو دوسروں کے کام آئے\nاپنے لیے تو سبھی جیتے ہیں", "بہترین جواب وہ ہے جو خاموشی سے دیا جائے\nیہ سب سے زیادہ اثر کرتا ہے", "بہترین دوست وہ ہے جو آپ کو گناہوں سے روکے\nاور نیکی کی طرف راغب کرے", "بہترین شخص وہ ہے جس کے ہاتھ اور زبان سے\nدوسرے مسلمان محفوظ رہیں", "بہترین کلام اللہ کا کلام ہے\nاور بہترین راستہ محمد صلی اللہ علیہ وسلم کا راستہ ہے", "بہترین دن جمعہ کا دن ہے\nاس دن دعائیں قبول ہوتی ہیں", "بہترین رات شب قدر کی رات ہے\nیہ ہزار مہینوں سے بہتر ہے", "بہترین صدقہ وہ ہے جو چھپا کر دیا جائے\nدکھاوے کا صدقہ قبول نہیں ہوتا", "بہترین عمل وہ ہے جو ہمیشہ کیا جائے\nچاہے وہ تھوڑا ہی کیوں نہ ہو", "بہترین انسان وہ ہے جو لوگوں کو فائدہ پہنچائے\nنقصان تو شیطان بھی پہنچاتا ہے" ],
    khubsurat: [ "تمہاری آنکھیں بہت خوبصورت ہیں\nجیسے کسی نے جھیل میں کنول رکھ دیے ہوں", "یہ دنیا کتنی خوبصورت ہے\nاگر دیکھنے والی آنکھ خوبصورت ہو", "خوبصورت لمحات ہمیشہ یاد رہتے ہیں\nچاہے وہ کتنے ہی مختصر کیوں نہ ہوں", "تیرا حسن ہے یا کوئی خوبصورت خواب\nجسے دیکھ کر آنکھیں کھلنا نہیں چاہتیں", "خوبصورت ہر وہ چیز ہے جو دل کو بھائے\nچاہے وہ دنیا کی نظر میں کیسی بھی ہو", "تیری مسکراہٹ اتنی خوبصورت ہے\nکہ پھول بھی دیکھ کر شرما جائیں", "یہ خوبصورت شام اور تیرا ساتھ\nاس سے بڑھ کر اور کیا چاہیے", "خوبصورت چہرے تو بہت ملتے ہیں\nمگر خوبصورت دل قسمت والوں کو ملتا ہے", "تیری باتیں اتنی خوبصورت ہیں\nکہ دل کرتا ہے بس سنتا ہی رہوں", "یہ خوبصورت منظر اور ٹھنڈی ہوا\nسب کچھ تیری یاد دلا رہا ہے", "خوبصورت لوگ ہمیشہ اچھے نہیں ہوتے\nمگر اچھے لوگ ہمیشہ خوبصورت ہوتے ہیں", "تیری زلفیں اتنی خوبصورت ہیں\nجیسے کالی گھٹا چھا گئی ہو", "یہ خوبصورت رات اور چاند کا نور\nسب کچھ تیرے حسن کا عکاس ہے", "خوبصورت یادیں انسان کو جینے کا حوصلہ دیتی ہیں\nجب سب کچھ ختم ہو جاتا ہے", "تیری سادگی اتنی خوبصورت ہے\nکہ بناوٹ بھی اس پر قربان ہو جائے", "یہ خوبصورت خواب کبھی نہ ٹوٹے\nجس میں تم میرے ساتھ ہو", "خوبصورت دل کی تلاش کرو\nخوبصورت چہرے تو دھوکا دیتے ہیں", "تیری آواز اتنی خوبصورت ہے\nکہ کوئل بھی سن کر چپ ہو جائے", "یہ خوبصورت زندگی ایک بار ملتی ہے\nاسے ہنس کر گزارو", "خوبصورت سوچ انسان کو خوبصورت بنا دیتی ہے\nچاہے اس کی شکل کیسی بھی ہو", "تیرا ہر انداز اتنا خوبصورت ہے\nکہ دل کرتا ہے بس دیکھتا ہی رہوں", "یہ خوبصورت پھول اور ان کی خوشبو\nسب کچھ تیرے آنے کا پتا دے رہے ہیں", "خوبصورت وہ نہیں جو آئینے میں نظر آئے\nخوبصورت وہ ہے جو دل میں اتر جائے", "تیری دوستی اتنی خوبصورت ہے\nکہ اس کے آگے ہر رشتہ پھیکا لگتا ہے", "یہ خوبصورت دنیا خدا کی نشانی ہے\nاس کی قدر کرو", "خوبصورت الفاظ تو سبھی کہہ لیتے ہیں\nمگر خوبصورت عمل کوئی کوئی کرتا ہے", "تیرا انتظار بھی اتنا خوبصورت ہے\nکہ دل کرتا ہے تو کبھی نہ آئے", "یہ خوبصورت بارش اور مٹی کی خوشبو\nسب کچھ تیرے بچپن کی یاد دلا رہا ہے", "خوبصورت بننا ہے تو اخلاق کو سنوارو\nکپڑے تو بے جان چیزوں کو بھی پہنائے جاتے ہیں", "تیری ہر ادا اتنی خوبصورت ہے\nکہ اس پر کتاب لکھی جا سکتی ہے", "یہ خوبصورت صبح اور پرندوں کا شور\nسب کچھ ایک نئی امید دے رہا ہے", "خوبصورت وہ ہے جس کی سیرت اچھی ہو\nصورت تو وقت کے ساتھ بدل جاتی ہے", "تیری محبت اتنی خوبصورت ہے\nکہ اس کے لیے ہر قربانی دی جا سکتی ہے", "یہ خوبصورت جھرنے اور ان کا شور\nسب کچھ زندگی کا نغمہ سنا رہے ہیں", "خوبصورت دل ہو تو ہر کوئی خوبصورت لگتا ہے\nورنہ چاند میں بھی داغ نظر آتا ہے", "تیری جدائی بھی اتنی خوبصورت ہے\nکہ اس میں بھی جینے کا مزہ آ رہا ہے", "یہ خوبصورت پہاڑ اور ان کی بلندی\nسب کچھ انسان کو اس کی اوقات یاد دلا رہے ہیں", "خوبصورت بننا ہے تو سچ بولو\nجھوٹ تو انسان کو بدصورت بنا دیتا ہے", "تیرا ہر خواب اتنا خوبصورت ہے\nکہ دل کرتا ہے کبھی نہ جاگوں", "یہ خوبصورت سمندر اور اس کی لہریں\nسب کچھ زندگی کے اتار چڑھاؤ کا درس دے رہی ہیں", "خوبصورت وہ ہے جو دوسروں کو خوش رکھے\nاپنے لیے تو سبھی جیتے ہیں", "تیری یاد بھی اتنی خوبصورت ہے\nکہ اس کے سہارے زندگی گزاری جا سکتی ہے", "یہ خوبصورت قوس قزح اور اس کے رنگ\nسب کچھ زندگی کی خوبصورتی کا ثبوت ہیں", "خوبصورت بننا ہے تو علم حاصل کرو\nجہالت تو انسان کو جانور بنا دیتی ہے", "تیرا غصہ بھی اتنا خوبصورت ہے\nکہ دل کرتا ہے تجھے بار بار ستاؤں", "یہ خوبصورت کائنات خدا کی تخلیق ہے\nاس پر غور و فکر کرو", "خوبصورت وہ ہے جو معاف کرنا جانتا ہو\nبدلہ تو ہر کوئی لے لیتا ہے", "تیرا ہر وعدہ اتنا خوبصورت ہے\nکہ اس کے ٹوٹنے کا بھی غم نہیں", "یہ خوبصورت ستارے اور ان کی چمک\nسب کچھ امید کا پیغام دے رہے ہیں", "خوبصورت بننا ہے تو شکر ادا کرو\nناشکری تو نعمتوں کو چھین لیتی ہے" ],
    allama_iqbal: [ "خودی کو کر بلند اتنا کہ ہر تقدیر سے پہلے\nخدا بندے سے خود پوچھے بتا تیری رضا کیا ہے", "ستاروں سے آگے جہاں اور بھی ہیں\nابھی عشق کے امتحاں اور بھی ہیں", "نہیں ہے نا امید اقبال اپنی کشت ویراں سے\nذرا نم ہو تو یہ مٹی بہت زرخیز ہے ساقی", "تندیٔ بادِ مخالف سے نہ گھبرا اے عقاب\nیہ تو چلتی ہے تجھے اونچا اڑانے کے لیے", "عمل سے زندگی بنتی ہے جنت بھی جہنم بھی\nیہ خاکی اپنی فطرت میں نہ نوری ہے نہ ناری ہے", "ہزاروں سال نرگس اپنی بے نوری پہ روتی ہے\nبڑی مشکل سے ہوتا ہے چمن میں دیدہ ور پیدا", "مانا کہ تیری دید کے قابل نہیں ہوں میں\nتو میرا شوق دیکھ، مرا انتظار دیکھ", "اپنے من میں ڈوب کر پا جا سراغ زندگی\nتو اگر میرا نہیں بنتا نہ بن، اپنا تو بن", "عقابی روح جب بیدار ہوتی ہے جوانوں میں\nنظر آتی ہے ان کو اپنی منزل آسمانوں میں", "کیوں منتیں مانگتا ہے اوروں کے دربار سے اقبال\nوہ کون سا کام ہے جو ہوتا نہیں تیرے پروردگار سے", "دنیا کی محفلوں سے اکتا گیا ہوں یا رب\nکیا لطف انجمن کا جب دل ہی بجھ گیا ہو", "تو شاہیں ہے پرواز ہے کام تیرا\nتیرے سامنے آسماں اور بھی ہیں", "مٹادے اپنی ہستی کو اگر کچھ مرتبہ چاہے\nکہ دانہ خاک میں مل کر گل و گلزار ہوتا ہے", "افراد کے ہاتھوں میں ہے اقوام کی تقدیر\nہر فرد ہے ملت کے مقدر کا ستارہ", "اندازِ بیاں گرچہ بہت شوخ نہیں ہے\nشاید کہ اتر جائے ترے دل میں مری بات", "مسجد تو بنا دی شب بھر میں ایماں کی حرارت والوں نے\nمن اپنا پرانا پاپی ہے، برسوں میں نمازی بن نہ سکا", "باطل سے دبنے والے اے آسماں نہیں ہم\nسو بار کر چکا ہے تو امتحاں ہمارا", "ہاتھوں کی لکیروں پہ نہ جا اے غافل\nنصیب ان کے بھی ہوتے ہیں جن کے ہاتھ نہیں ہوتے", "جھپٹنا، پلٹنا، پلٹ کر جھپٹنا\nلہو گرم رکھنے کا ہے اک بہانہ", "نشہ پلا کے گرانا تو سب کو آتا ہے\nمزا تو تب ہے کہ گرتوں کو تھام لے ساقی", "کھول آنکھ، زمیں دیکھ، فلک دیکھ، فضا دیکھ\nمشرق سے ابھرتے ہوئے سورج کو ذرا دیکھ", "نہیں تیرا نشیمن قصرِ سلطانی کے گنبد پر\nتو شاہیں ہے، بسیرا کر پہاڑوں کی چٹانوں میں", "یہ گھڑی محشر کی ہے، تو عرصۂ محشر میں ہے\nپیش کر غافل، عمل کوئی اگر دفتر میں ہے", "زندگی ہو مری پروانے کی صورت یا رب\nعلم کی شمع سے ہو مجھ کو محبت یا رب", "ترے عشق کی انتہا چاہتا ہوں\nمری سادگی دیکھ کیا چاہتا ہوں", "دلوں کی عمارتوں میں کہیں بندگی نہیں\nاور پتھر کی مسجدوں میں خدا ڈھونڈتے ہیں لوگ", "نگاہِ فقر میں شانِ سکندری کیا ہے\nخراج کی جو گدا ہو، وہ قیصری کیا ہے", "آئینِ جواں مرداں، حق گوئی و بے باکی\nاللہ کے شیروں کو آتی نہیں روباہی", "کافر ہے تو شمشیر پہ کرتا ہے بھروسا\nمومن ہے تو بے تیغ بھی لڑتا ہے سپاہی", "سجدوں کے عوض فردوس ملے، یہ بات مجھے منظور نہیں\nبے لوث عبادت کرتا ہوں، بندہ ہوں، ترا مزدور نہیں", "دلِ مردہ، دل نہیں ہے، اسے زندہ کر دوبارہ\nکہ یہی ہے امتوں کے مرضِ کہن کا چارہ", "عروجِ آدمِ خاکی سے انجم سہمے جاتے ہیں\nکہ یہ ٹوٹا ہوا تارا، مہِ کامل نہ بن جائے", "بھروسہ کر نہیں سکتے غلاموں کی بصیرت پر\nکہ دنیا میں فقط مردانِ حر کی آنکھ ہے بینا", "یہ ایک سجدہ جسے تو گراں سمجھتا ہے\nہزار سجدوں سے دیتا ہے آدمی کو نجات", "اسرارِ خودی میں ہے خدائی\nخودی کو جو سمجھا، خدا کو سمجھا", "وہ علم نہیں، زہر ہے احرار کے حق میں\nجس علم کا حاصل ہو جہاں میں دو کفِ جو", "مومن ہے تو کرتا ہے فقیری میں بھی شاہی\nمومن نہیں تو مردِ مسلماں بھی ہے کافر", "اقبال بڑا اپدیشک ہے، من باتوں میں موہ لیتا ہے\nگفتار کا یہ غازی تو بنا، کردار کا غazi بن نہ سکا", "تیری دعا سے قضا تو بدل نہیں سکتی\nمگر ہے اس سے یہ ممکن کہ تو بدل جائے", "حیا نہیں ہے زمانے کی آنکھ میں باقی\nخدا کرے کہ جوانی تری رہے بے داغ", "کبھی اے نوجواں مسلم! تدبر بھی کیا تو نے\nوہ کیا گردوں تھا تو جس کا ہے اک ٹوٹا ہوا تارا", "یقیں محکم، عمل پیہم، محبت فاتحِ عالم\nجہادِ زندگانی میں ہیں یہ مردوں کی شمشیریں", "پرواز ہے دونوں کی اسی ایک فضا میں\nکرگس کا جہاں اور ہے، شاہیں کا جہاں اور", "نکل کر خانقاہوں سے ادا کر رسمِ شبیری\nکہ فقرِ خانقاہی ہے فقط اندوہ و دلگیری", "تیرے آزاد بندوں کی نہ یہ دنیا، نہ وہ دنیا\nیہاں مرنے کی پابندی، وہاں جینے کی پابندی", "یہ شہادت گہِ الفت میں قدم رکھنا ہے\nلوگ آساں سمجھتے ہیں مسلماں ہونا", "خرد کو غلامی سے آزاد کر\nجوانوں کو پیروں کا استاد کر", "ہو حلقۂ یاراں تو بریشم کی طرح نرم\nرزمِ حق و باطل ہو تو فولاد ہے مومن", "دل سے جو بات نکلتی ہے، اثر رکھتی ہے\nپر نہیں، طاقت پرواز مگر رکھتی ہے", "آج بھی ہو جو براہیم کا ایماں پیدا\nآگ کر سکتی ہے اندازِ گلستاں پیدا" ],
    ahmad_faraz: [ "اب کے ہم بچھڑے تو شاید کبھی خوابوں میں ملیں\nجس طرح سوکھے ہوئے پھول کتابوں میں ملیں", "رنجش ہی سہی دل ہی دکھانے کے لیے آ\nآ پھر سے مجھے چھوڑ کے جانے کے لیے آ", "سنا ہے لوگ اسے آنکھ بھر کے دیکھتے ہیں\nتو اس کے شہر میں کچھ دن ٹھہر کے دیکھتے ہیں", "اس زندگی میں اتنی فراغت کسے نصیب\nاتنا نہ یاد آ کہ تجھے بھول جائیں ہم", "دوست بن کر بھی نہیں ساتھ نبھانے والا\nوہی انداز ہے ظالم کا زمانے والا", "یہ کیا کہ سب سے بیاں دل کی حالتیں کرنی\nفراز تجھ کو نہ آئیں محبتیں کرنی", "کون دیتا ہے عمر بھر کا سہارا فراز\nلوگ تو جنازے میں بھی کندھے بدلتے رہتے ہیں", "میں اسے بھول بھی جاؤں تو کیسی مشکل ہے\nاس نے جو زخم دیے ہیں وہ بھرنے نہیں دیتا", "تم تکلف کو بھی اخلاص سمجھتے ہو فراز\nدوست ہوتا نہیں ہر ہاتھ ملانے والا", "اب اسے روز نہ سوچوں تو بدن ٹوٹتا ہے فراز\nاک عمر ہو گئی ہے اس کی یاد کا نشہ کرتے کرتے", "وہ شخص ایک چھوٹی سی بات پر یوں روٹھ کر چل دیا\nجیسے اسے صدیوں سے کسی بہانے کی تلاش تھی", "ہم بھی وہ ہیں جو کبھی کسی کے پیچھے نہیں کھڑے ہوتے\nجہاں بیٹھ جائیں، لائن وہیں سے شروع ہوتی ہے", "شکوہ ظلمت شب سے تو کہیں بہتر تھا\nاپنے حصے کی کوئی شمع جلاتے جاتے", "اب کے تجدید وفا کا نہیں امکاں جاناں\nیاد کیا تجھ کو دلائیں تیرا پیماں جاناں", "دل بھی توڑا تو سلیقے سے نہ توڑا تم نے\nبے وفائی کے بھی آداب ہوا کرتے ہیں", "اس سے پہلے کہ بے وفا ہو جائیں\nکیوں نہ اے دوست ہم جدا ہو جائیں", "میں مر بھی جاؤں تو اسے خبر نہ کرنا فراز\nکہ وہ پریشان ہو گیا تو میرا دل پھر سے دھڑک اٹھے گا", "وہ ہم سفر تھا مگر اس سے ہم نوائی نہ تھی\nکہ دھوپ چھاؤں کا عالم رہا، جدائی نہ تھی", "اب اور کیا کسی سے مراسم بڑھائیں ہم\nیہ بھی بہت ہے تجھ کو اگر بھول جائیں ہم", "دشمنوں کے ساتھ میرے دوست بھی آزاد ہیں\nدیکھنا ہے کھینچتا ہے مجھ پہ پہلا تیر کون", "اسے ہم یاد آتے ہیں مگر فرصت کے لمحوں میں\nمگر یہ بات بھی سچ ہے اسے فرصت نہیں ملتی", "اب کس کا جشن مناتے ہو، اس دیس کا جو تقسیم ہوا\nاب کس کے گیت سناتے ہو، اس تن من کا جو دو نیم ہوا", "ہم نے جس جس کو بھی چاہا تیرے ہجراں میں وہ لوگ\nآتے جاتے ہوئے موسم تھے، زمانہ تو تھا", "تو خدا ہے نہ مرا عشق فرشتوں جیسا\nدونوں انساں ہیں تو کیوں اتنے حجابوں میں ملیں", "عشق کی ایک ہی منزل ہے، ہر اک راہ گزر\nہم بھی تنہا تھے مگر لوگ بھی juinha نکلے", "وہیں پھرتا ہوں میں بھی خاک بسر\nاس بھری کائنات میں تنہا", "یہاں بھی ہو، وہاں بھی ہو، مگر ہو تم کہاں آخر\nکوئی منزل نہیں ملتی جہاں تک راہ گزر جائے", "کس کو فرصت ہے کہ ملتا رہے ہر اک سے گلے\nاپنی ہی ذات میں کتنا ہے سفر، کیا جانیں", "ہم تو سمجھے تھے کہ اک زخم ہے بھر جائے گا\nکیا خبر تھی کہ رگ جاں میں اتر جائے گا", "اب کسے ڈھونڈتے ہو شہر میں فراز\nوہ تو دنیا ہی چھوڑ گیا تجھے ویران کر کے", "کس کو سنائیں حال دلِ بے قرار کا\nدنیا ہے جیسے دشمن ہر اک غم گسار کا", "کب تک رہو گے آخر یوں دور دور ہم سے\nملنا پڑے گا آخر اک دن ضرور ہم سے", "یہ عشق بھی کیا ہے، اسے اپنائے کوئی اور\nچاہیں ہم، اور اسے لے جائے کوئی اور", "اس قدر بھی تو نہ جذبات پہ قابو رکھو\nتھک گئے ہو تو مرے کاندھے پہ بازو رکھو", "یہاں لباس کی قیمت ہے، آدمی کی نہیں\nمجھے گلاس بڑے دے، شراب کم کر دے", "میں جب بھی چاہوں اسے چھو کے دیکھ سکتا ہوں\nمگر وہ شخص کہ لگتا ہے اب بھی خواب ایسا", "عمر بھر کون نبھاتا ہے تعلق اتنا\nاے مری جان کے دشمن تجھے اللہ رکھے", "وہ تو خوشبو ہے، ہواؤں میں بکھر جائے گا\nمسئلہ پھول کا ہے، پھول کدھر جائے گا", "اب تو ہاتھوں سے لکیریں بھی مٹی جاتی ہیں\nاس کو کھو کر تو مرے پاس رہا کچھ بھی نہیں", "میں نے چاہا تھا کہ زخموں کا کوئی نام رکھوں\nپر یہ دل ہے کہ کسی بات پہ راضی نہ ہوا", "زندگی سے یہی گلہ ہے مجھے\nتو بہت دیر سے ملا ہے مجھے", "ہم محبت میں بھی توحید کے قائل ہیں فراز\nایک ہی شخص کو محبوب بنائے رکھا", "یہ علم کا سودا، یہ رسالے، یہ کتابیں\nاک شخص کی یادوں کو بھلانے کے لیے ہیں", "تم بھی خفا ہو لوگ بھی برہم ہیں دوستو\nاب ہو چلا یقیں کہ برے ہم ہیں دوستو", "کچھ تو مجبوریاں رہی ہوں گی\nیوں کوئی بے وفا نہیں ہوتا", "تو سامنے ہے تو پھر کیوں یقیں نہیں آتا\nیہ بار بار جو آنکھوں کو مل رہا ہوں میں", "ہم اپنی روح ترے جسم میں چھوڑ آئے ہیں\nتجھے گلے سے لگانا تو اک بہانہ تھا", "اب بھی برسات کی راتوں میں بدن ٹوٹتا ہے\nجاگ اٹھتی ہیں عجب خواہشیں انگڑائی کی", "وہ بے وفا نہ تھا یوں ہی بد نام ہو گیا فراز\nہزاروں چاہنے والے تھے کس کس سے وفا کرتا" ],
    mir_taqi_mir: [ "الٹی ہو گئیں سب تدبیریں کچھ نہ دوا نے کام کیا\nدیکھا اس بیماریِ دل نے آخر کام تمام کیا", "پتّہ پتّہ بوٹا بوٹا حال ہمارا جانے ہے\nجانے نہ جانے گل ہی نہ جانے باغ تو سارا جانے ہے", "میر کیا سادہ ہیں، بیمار ہوئے جس کے سبب\nاسی عطار کے لونڈے سے دوا لیتے ہیں", "شام ہی سے بجھا سا رہتا ہے\nدل ہوا ہے چراغ مفلس کا", "مرگ اک ماندگی کا وقفہ ہے\nیعنی آگے چلیں گے دم لے کر", "یاد اس کی اتنی خوب نہیں میر باز آ\nنادان پھر وہ جی سے بھلایا نہ جائے گا", "دل کی ویرانی کا کیا مذکور ہے\nیہ نگر سو مرتبہ لوٹا گیا", "دکھائی دیں یوں کہ بے خود کیا\nہمیں آپ سے بھی جدا کر چلے", "ہستی اپنی حباب کی سی ہے\nیہ نمائش سراب کی سی ہے", "فقیرانہ آئے صدا کر چلے\nمیاں خوش رہو ہم دعا کر چلے", "اب تو جاتے ہیں بتکدے سے میر\nپھر ملیں گے اگر خدا لایا", "عشق اک میر بھاری پتھر ہے\nکب یہ تجھ ناتواں سے اٹھتا ہے", "آگے دریا تھا جو چڑھتا تھا ہر اک موج کے ساتھ\nاب جو دیکھا تو وہی گرد کا صحرا نکلا", "مر گئے پر کتاب باقی ہے\nدل میں اک اضطراب باقی ہے", "ہوتا ہے نہاں گرد میں صحرا مرے ہوتے\nگستاخ ہے پر اتنا بھی گستاخ نہیں میں", "مرتے ہیں آرزو میں مرنے کی\nموت آتی ہے پر نہیں آتی", "وہ آئے بزم میں اتنا تو میر نے دیکھا\nپھر اس کے بعد چراغوں میں روشنی نہ رہی", "سارے عالم پر ہوں میں چھایا ہوا\nمستند ہے میرا فرمایا ہوا", "میرے سنگِ مزار پر فرہاد\nرکھ کے تیشہ کہے ہے یا استاد", "اب کر کے فراموش تو ناشاد کرو گے\nپر ہم جو نہ ہوں گے تو بہت یاد کرو گے", "یوں اٹھے آہ اس گلی سے ہم\nجیسے کوئی جہاں سے اٹھتا ہے", "کیا کہوں تم سے میں کہ کیا ہے عشق\nجان کا روگ ہے، بلا ہے عشق", "وصل اس کا خدا نصیب کرے\nمیر دل چاہتا ہے کیا کیا کچھ", "سب پہ جس بار نے گرانی کی\nاس کو یہ ناتواں اٹھا لایا", "عہدِ جوانی رو رو کاٹا، پیری میں لیں آنکھیں موند\nیعنی رات بہت تھے جاگے، صبح ہوئی آرام کیا", "اب حال ہمارا کیا پوچھو، ہم حال سے اپنے گزرے ہیں\nاک دوست تھا جس کو کھو کر ہم، ہر دوست سے اپنے گزرے ہیں", "ہم ہوئے، تم ہوئے کہ میر ہوئے\nاس کی زلفوں کے سب اسیر ہوئے", "آبلے کی طرح ٹھیس لگی، پھوٹ بہے\nدردمندی میں گئی ساری جوانی اپنی", "کیا اعتبار یہاں کا، پھر اس دیار کا کیا\nجہاں سے میر چلے، وہیں قرار پایا", "دل وہ نگر نہیں کہ پھر آباد ہو سکے\nپچھتاؤ گے، سنو ہو، یہ بستی اجاڑ کر", "آفاق کی منزل سے گیا کون سلامت\nاسباب لٹا راہ میں یاں ہر سفری کا", "عشق ہی عشق ہے جہاں دیکھو\nسارے عالم میں بھر رہا ہے عشق", "ابتداے عشق ہے روتا ہے کیا\nآگے آگے دیکھیے ہوتا ہے کیا", "مرثیہ دل کا لکھ دیا ہم نے\nجیسے کوئی کتاب ہوتی ہے", "عشق کرتے ہیں اس پری رو سے\nمیر صاحب بھی کیا دوانے ہیں", "رات مجلس میں ترے حسن کے شعلے کے حضور\nشمع کے منہ پہ جو دیکھا تو کہیں نور نہ تھا", "میر جی چاہتا ہے کیا کیا کچھ\nجب وہ کافر نگاہ کرتا ہے", "دل مجھے اس گلی میں لے جا کر\nاور بھی خاک میں ملا لایا", "میں جو بولا کہا کہ یہ آواز\nاسی خانہ خراب کی سی ہے", "شعر میرے ہیں سب خواص پسند\nپر مجھے گفتگو عوام سے ہے", "زندگی ہے یا کوئی طوفان ہے\nہم تو اس جینے کے ہاتھوں مر چلے", "کیا جانوں لوگ کہتے ہیں کس کو سکونِ دل\nآیا نہیں یہ لفظ تو اس کام کے لئے", "رہی نہ گفتگو کوئی، نہ کوئی بات ہوئی\nخموش بیٹھے رہے، اور رات ہو گئی", "مت سہل ہمیں جانو، پھرتا ہے فلک برسوں\nتب خاک کے پردے سے انسان نکلتے ہیں", "سرہانے میر کے آہستہ بولو\nابھی ٹک روتے روتے سو گیا ہے", "یوں پکارے ہیں مجھے کوچۂ جاناں والے\nادھر آ بے، ابے او، چکنی چپڑی باتوں والے", "مجھ کو شاعر نہ کہو میر کہ صاحب میں نے\nدرد و غم کتنے کیے جمع تو دیوان کیا", "یک نگاہِ گرم پر دل کا معاملہ طے ہوا\nہم نے سمجھا تھا محبت میں بہت جھگڑا ہے", "آگ تھے ابتدائے عشق میں ہم\nا، انتہا ہے یہ", "بے خودی لے گئی کہاں ہم کو\nدیر سے انتظار ہے اپنا" ],
    jaun_elia: [ "جو گزاری نہ جا سکی ہم سے\nہم نے وہ زندگی گزاری ہے", "علاج یہ ہے کہ مجبور کر دیا جاؤں\nوگرنہ یوں تو کسی کی نہیں سنی میں نے", "کون اس گھر کی دیکھ بھال کرے\nروز اک چیز ٹوٹ جاتی ہے", "میں بھی حاضر تھا وہاں دار و رسن بھی تھا\nیہ حال تھا کہ وقت کا بوجھ بھی مجھ پر تھا", "شاید اس لیے مجھے نیند نہیں آتی\nکیونکہ میں نے ایک خواب کو زندہ رکھا ہے", "عمر بھر کا حساب مانگتی ہے\nیہ جو آنکھ ہے، یہ نیند مانگتی ہے", "کتنے عیش سے رہتے ہوں گے کتنے اتراتے ہوں گے\nجانے کیسے لوگ وہ ہوں گے جو اس کو بھاتے ہوں گے", "اب نہیں کوئی بات خطرے کی\nاب سبھی کو سبھی سے خطرہ ہے", "میں رہا عمر بھر جدا خود سے\nیاد میں خود کو عمر بھر آیا", "زندگی کس طرح بسر ہوگی\nدل نہیں لگ رہا محبت میں", "ایک ہی حادثہ تو ہے اور وہ یہ کہ آج تک\nبات نہیں کہی گئی، بات نہیں سنی گئی", "بہت نزدیک آتی جا رہی ہو\nبچھڑنے کا ارادہ کر لیا کیا؟", "خود کو تباہ کر لیا اور ملال بھی نہیں\nاے زندگی! تیرا کوئی جواب بھی نہیں", "کیا بتاؤں کہ مر نہیں پاتا\nجیتے جی جب سے مر گیا ہوں میں", "یہ مجھے چین کیوں نہیں پڑتا\nایک ہی شخص تھا جہان میں کیا؟", "شرم، دہشت، جھجک، پریشانی\nناز سے کام کیوں نہیں لیتیں", "اپنی محرومی کے احساس سے شرمندہ ہیں\nخود نہیں رکھتے تو اوروں کے بجھاتے ہیں چراغ", "کیسے کہیں کہ تجھ کو بھی ہم سے ہے واسطہ کوئی\nتو نے تو ہم سے آج تک کوئی گلہ نہیں کیا", "رخصت ہوا تو آنکھ ملا کر نہیں گیا\nوہ کیوں گیا یہ بھی بتا کر نہیں گیا", "اب میں سارے جہاں میں ہوں اور تم\nتم کہو، اب کہاں نہیں ہوں میں", "ہے غنیمت کہ اسرار ہستی\nخود پہ کھولے، نہ میں نے، نہ تو نے", "نیا اک رشتہ پیدا کیوں کریں ہم\nبچھڑنا ہے تو جھگڑا کیوں کریں ہم", "اب تو ہر بات یاد رہتی ہے\nغالباً میں کسی کو بھول گیا", "بولتے کیوں نہیں مرے حق میں\nآبلے پڑ گئے زبان میں کیا", "تم جب آؤ گی تو کھویا ہوا پاؤ گی مجھے\nمیری تنہائی میں خوابوں کے سوا کچھ بھی نہیں", "حالتِ حال کے سبب، حالتِ حال ہی گئی\nشوق میں کچھ نہیں گیا، شوق کی زندگی گئی", "کتنا پر کیف ہے یہ عالم تنہائی\nجب تجھے سوچتا ہوں تو خود کو بھول جاتا ہوں", "ایک دل ہے کہ سنبھلتا ہی نہیں ہے مجھ سے\nایک میں ہوں کہ اسے اور بگاڑے جاؤں", "میں تو اس کے فراق میں چپ چاپ\nاپنے اندر ہی مر گیا ہوں میں", "یوں جو تکتا ہے آسمان کو تو\nکوئی رہتا ہے آسمان میں کیا", "اب مری کوئی زندگی ہی نہیں\nاب بھی تم میری زندگی ہو کیا؟", "کچھ بھی تو اپنے پاس نہیں ہے سوائے اس کے\nایک شخص کو ہم نے بھی کما رکھا ہے", "ساری دنیا کے غم ہمارے ہیں\nاور ستم یہ کہ ہم تمہارے ہیں", "کیا تکلف کریں یہ کہنے میں\nجو بھی خوش ہے ہم اس سے جلتے ہیں", "دل پریشاں ہے، کیا کیا جائے\nعقل دیوانی، کیا کیا جائے", "جرم میں ہم کمی کریں بھی تو کیوں\nتم سزا بھی تو کم نہیں کرتے", "خود سے بھی دور ہو گیا ہوں میں\nتم سے ملنے کی آرزو میں", "یہ بہت غم کی بات ہو شاید\nاب تو غم بھی گنوا چکا ہوں میں", "ہم جی رہے ہیں کوئی بہانہ کیے بغیر\nاس کے بغیر، اس کی تمنا کیے بغیر", "اب وہ بھی نہیں، اس کی یاد بھی نہیں\nکتنا آباد تھا میرا ویرانہ کبھی", "کتنی دلکش ہو تم، کتنا دل جو ہوں میں\nکیا ستم ہے کہ ہم لوگ مر جائیں گے", "دل نے وفا کے نام پر کارِ وفا نہیں کیا\nخود کو ہلاک کر لیا، خود کو فدا نہیں کیا", "بے قراری سی بے قراری ہے\nوصل ہے اور فراق طاری ہے", "میری ہر بات بے اثر ہی رہی\nنقص ہے کچھ مرے بیان میں کیا", "کون آئے گا یہاں، کوئی نہ آیا ہوگا\nمیرا دروازہ ہواؤں نے ہلایا ہوگا", "ہم کہ مایوس نہیں ہیں، انہیں کھو کر لیکن\nہم پہ جو گزری ہے، وہ بات نہ پوچھے کوئی", "یہ غم کیا دل کی عادت ہے؟ نہیں تو\nکسی سے کچھ شکایت ہے؟ نہیں تو", "اک شخص کر رہا ہے ابھی تک وفا کا ذکر\nکاش اس زباں دراز کا منہ نوچ لے کوئی", "میں بھی بہت عجیب ہوں، اتنا عجیب ہوں کہ بس\nخود کو تباہ کر لیا اور ملال بھی نہیں", "کس لیے دیکھتی ہو آئینہ\nتم تو خود سے بھی خوبصورت ہو" ]
};

// --- Global Variables & Constants ---
const ACCESS_PASSWORD = "334499";
const USER_SHAYARI_KEY = 'userShayaris_v2'; 
const FAVORITES_KEY = 'favoritedShayaris_v2'; 
const THEME_KEY = 'shayariAppTheme_v2'; 

let userAddedShayaris = JSON.parse(localStorage.getItem(USER_SHAYARI_KEY)) || {};
let shayaris = {};
let currentCategory = 'muhabbat';
let favoritedShayaris = JSON.parse(localStorage.getItem(FAVORITES_KEY)) || {};
let isShowingFavorites = false;

// --- DOM Elements ---
const body = document.body;
const categoryButtons = document.querySelectorAll('.category-button');
const sideMenu = document.getElementById('sideMenu');
const menuOverlay = document.getElementById('menuOverlay');
const shayariListContainer = document.getElementById('shayari-list-container');
const shayariView = document.getElementById('shayari-view');
const addShayariView = document.getElementById('add-shayari-view');
const newShayariTextarea = document.getElementById('new-shayari-text');
const newShayariCategorySelect = document.getElementById('new-shayari-category');
const submitNewShayariBtn = document.getElementById('submit-new-shayari');
const cancelAddShayariBtn = document.getElementById('cancel-add-shayari');

// --- Core Functions ---

function combineShayaris() {
    shayaris = JSON.parse(JSON.stringify(defaultShayaris));
    for (const category in userAddedShayaris) {
        if (userAddedShayaris.hasOwnProperty(category)) {
            if (!shayaris[category]) {
                shayaris[category] = [];
            }
            shayaris[category] = [...userAddedShayaris[category], ...shayaris[category]];
        }
    }
}

function renderShayaris() {
    shayariListContainer.innerHTML = ''; 
    combineShayaris();
    const currentShayariList = shayaris[currentCategory] || [];

    if (currentShayariList.length === 0) {
        shayariListContainer.innerHTML = `<div class="individual-shayari-card"><p>اس کیٹیگری میں کوئی شاعری دستیاب نہیں۔</p></div>`;
        return;
    }

    currentShayariList.forEach((shayariText, index) => {
        // Create Shayari Card
        const card = createShayariCard(shayariText, index + 1);
        shayariListContainer.appendChild(card);

        // Add ad placeholder after every 5th shayari
        if ((index + 1) % 5 === 0 && (index + 1) < currentShayariList.length) {
            const adDiv = document.createElement('div');
            adDiv.className = 'ad-placeholder';
            adDiv.textContent = 'اشتہار یہاں دکھایا جائے گا';
            shayariListContainer.appendChild(adDiv);
        }
    });
}

function createShayariCard(shayariText, number) {
    const card = document.createElement('div');
    card.className = 'individual-shayari-card';

    // Add Numbering
    const numberDiv = document.createElement('div');
    numberDiv.className = 'shayari-number';
    numberDiv.textContent = number;
    card.appendChild(numberDiv);

    const p = document.createElement('p');
    p.textContent = shayariText;
    
    const actionsDiv = document.createElement('div');
    actionsDiv.className = 'shayari-card-actions';

    const favoriteButton = createActionButton('favorite', 'fa-heart', 'پسند کریں', () => toggleFavorite(shayariText, favoriteButton));
    if (favoritedShayaris[shayariText]) {
        favoriteButton.classList.add('favorited');
    }

    const copyButton = createActionButton('copy', 'fa-copy', 'کاپی کریں', () => copyToClipboard(shayariText, copyButton));

    actionsDiv.appendChild(favoriteButton);
    actionsDiv.appendChild(copyButton);

    card.appendChild(p);
    card.appendChild(actionsDiv);
    return card;
}


function createActionButton(className, iconClass, text, onClick) {
    const button = document.createElement('button');
    button.className = `action-button ${className}`;
    button.innerHTML = `<i class="fas ${iconClass}"></i><span>${text}</span>`;
    button.onclick = onClick;
    return button;
}

function changeCategory(newCategory) {
    isShowingFavorites = false;
    currentCategory = newCategory;
    
    document.querySelector('.category-button.active')?.classList.remove('active');
    document.querySelector(`.category-button[data-category="${newCategory}"]`).classList.add('active');
    document.querySelector('h1').textContent = document.querySelector(`.category-button[data-category="${newCategory}"]`).textContent + " شاعری";
    
    showView('shayari');
    renderShayaris();
}

// --- Feature Functions (Favorites, Copy, Add) ---

function toggleFavorite(shayariText, button) {
    if (favoritedShayaris[shayariText]) {
        delete favoritedShayaris[shayariText];
        button.classList.remove('favorited');
    } else {
        favoritedShayaris[shayariText] = true;
        button.classList.add('favorited');
    }
    localStorage.setItem(FAVORITES_KEY, JSON.stringify(favoritedShayaris));
    
    if (isShowingFavorites) {
        showFavorites();
    }
}

function showFavorites() {
    isShowingFavorites = true;
    shayariListContainer.innerHTML = '';
    closeNav();

    const favs = Object.keys(favoritedShayaris);
    document.querySelector('h1').textContent = 'پسندیدہ شاعری';
    
    document.querySelector('.category-button.active')?.classList.remove('active');

    if (favs.length === 0) {
        shayariListContainer.innerHTML = `<div class="individual-shayari-card"><p>آپ نے ابھی تک کوئی شاعری پسند نہیں کی۔</p></div>`;
        return;
    }

    favs.forEach((shayariText, index) => {
        const card = createShayariCard(shayariText, index + 1);
        shayariListContainer.appendChild(card);

        // Add ad placeholder in favorites as well
        if ((index + 1) % 5 === 0 && (index + 1) < favs.length) {
            const adDiv = document.createElement('div');
            adDiv.className = 'ad-placeholder';
            adDiv.textContent = 'اشتہار یہاں دکھایا جائے گا';
            shayariListContainer.appendChild(adDiv);
        }
    });

    showView('shayari');
}

function copyToClipboard(text, button) {
    navigator.clipboard.writeText(text).then(() => {
        const originalText = button.querySelector('span').textContent;
        const originalColor = button.style.borderColor;
        button.querySelector('span').textContent = 'کاپی ہو گیا!';
        button.style.borderColor = '#2ecc71';
        button.style.color = '#2ecc71';
        setTimeout(() => {
            button.querySelector('span').textContent = originalText;
            button.style.borderColor = '';
            button.style.color = '';
        }, 2000);
    }).catch(err => {
        console.error('Copy failed', err);
        alert('کاپی کرنے میں ناکامی ہوئی۔');
    });
}

function handleAddShayari() {
    const text = newShayariTextarea.value.trim();
    const category = newShayariCategorySelect.value;

    if (!text) {
        alert('براہ کرم شاعری کا متن درج کریں۔');
        return;
    }

    if (!userAddedShayaris[category]) {
        userAddedShayaris[category] = [];
    }
    
    userAddedShayaris[category].unshift(text);
    localStorage.setItem(USER_SHAYARI_KEY, JSON.stringify(userAddedShayaris));

    newShayariTextarea.value = '';
    alert('آپ کی شاعری کامیابی سے شامل کر دی گئی ہے!');
    showView('shayari');
    changeCategory(category);
}

// --- UI & View Management ---

function showView(viewId) {
    if (viewId === 'shayari') {
        shayariView.style.display = 'block';
        addShayariView.style.display = 'none';
    } else if (viewId === 'add') {
        shayariView.style.display = 'none';
        addShayariView.style.display = 'flex';
    }
}

function showAddShayariForm() {
    closeNav();
    const password = prompt("شاعری شامل کرنے کے لیے ایڈمن پاس ورڈ درج کریں:", "");
    if (password === ACCESS_PASSWORD) {
        showView('add');
    } else if (password !== null) {
        alert('غلط پاس ورڈ!');
    }
}

// --- Theme & Menu Functions ---

function applyTheme(theme) {
    body.classList.remove('dark-theme', 'light-theme');
    body.classList.add(theme);
    localStorage.setItem(THEME_KEY, theme);
}

function toggleTheme() {
    const newTheme = body.classList.contains('dark-theme') ? 'light-theme' : 'dark-theme';
    applyTheme(newTheme);
    closeNav();
}

function openNav() {
    sideMenu.style.width = "320px";
    menuOverlay.classList.add('active');
}

function closeNav() {
    sideMenu.style.width = "0";
    menuOverlay.classList.remove('active');
}

// --- Event Listeners & Initializer ---

document.addEventListener('DOMContentLoaded', () => {
    const savedTheme = localStorage.getItem(THEME_KEY) || 'dark-theme';
    applyTheme(savedTheme);

    changeCategory(currentCategory);

    categoryButtons.forEach(button => {
        button.addEventListener('click', () => {
            const category = button.getAttribute('data-category');
            changeCategory(category);
        });
    });

    submitNewShayariBtn.addEventListener('click', handleAddShayari);
    cancelAddShayariBtn.addEventListener('click', () => {
        showView('shayari');
        changeCategory(currentCategory);
    });
});
</script>

</body>
