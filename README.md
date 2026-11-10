<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VELVET PARFUMS | عطور فيلقيت</title>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;700&family=Tajawal:wght@300;400;500;700&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-color: #f9f7f2;
            --card-bg: #ffffff;
            --accent-gold: #786e4f;
            --accent-gold-light: #9e926c;
            --text-dark: #2c2a29;
            --text-muted: #66625c;
            --border-color: #e8e4dc;
            --shadow: 0 10px 30px rgba(0,0,0,0.04);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Tajawal', sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-dark);
            line-height: 1.6;
            padding-bottom: 70px;
        }

        header {
            background-color: var(--card-bg);
            text-align: center;
            padding: 25px 20px;
            border-bottom: 1px solid var(--border-color);
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 4px 15px rgba(0,0,0,0.02);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .header-title-container {
            margin: 0 auto;
            text-align: center;
        }

        .logo-svg {
            width: 55px;
            height: 55px;
            margin-bottom: 5px;
        }

        .brand-title {
            font-family: 'Cinzel', serif;
            font-size: 20px;
            font-weight: 700;
            letter-spacing: 2px;
            color: var(--accent-gold);
        }

        .brand-subtitle {
            font-family: 'Cinzel', serif;
            font-size: 10px;
            letter-spacing: 2px;
            color: var(--text-muted);
            text-transform: uppercase;
        }

        .btn-admin-toggle {
            background: var(--bg-color);
            border: 1px solid var(--border-color);
            padding: 8px 14px;
            border-radius: 20px;
            cursor: pointer;
            font-size: 13px;
            color: var(--accent-gold);
            font-weight: bold;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 20px;
        }

        /* لوحة التحكم والإضافة السريعة */
        .admin-banner {
            display: none;
            background: #ffffff;
            border: 2px solid var(--accent-gold);
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 30px;
        }

        .admin-banner.active {
            display: block;
        }

        .admin-banner h3 {
            color: var(--accent-gold);
            font-size: 17px;
            margin-bottom: 15px;
            text-align: center;
        }

        .admin-form-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 12px;
            margin-bottom: 15px;
        }

        .admin-form-grid input, .admin-form-grid select, .admin-form-grid textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            font-size: 13px;
            outline: none;
            background: var(--bg-color);
        }

        .file-input-wrapper {
            grid-column: 1 / -1;
            background: #f2eee9;
            padding: 15px;
            border-radius: 6px;
            text-align: center;
            border: 1px dashed var(--accent-gold-light);
        }

        .btn-add {
            background-color: var(--accent-gold);
            color: white;
            border: none;
            padding: 12px;
            border-radius: 6px;
            font-weight: bold;
            cursor: pointer;
            width: 100%;
            font-size: 15px;
        }

        .btn-add:hover {
            background-color: var(--accent-gold-light);
        }

        /* التصنيفات والعرض */
        .categories-nav {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .cat-btn {
