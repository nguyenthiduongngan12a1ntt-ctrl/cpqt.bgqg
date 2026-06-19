# cpqt.bgqg
Portfolio: Phân Định Biên Giới Vùng Biên
# Clone the repository
git clone https://github.com/YOUR-USERNAME/cpqt.bgqg.git
cd cpqt.bgqg

# Create index.html and paste the code
echo "[<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio: Khung Pháp Lý Biên Giới Quốc Gia</title>
    <style>
        :root {
            --bg-pure: #ffffff;
            --bg-gradient: linear-gradient(135deg, #f5f9ff 0%, #e6f0fa 100%);
            --blue-dark: #002B66;
            --blue-medium: #0055CC;
            --blue-light: #3388FF;
            --blue-tint: #f0f6ff;
            --text-main: #1E293B;
            --text-muted: #64748B;
            --accent-red: #FF4D4D;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-pure);
            color: var(--text-main);
            line-height: 1.6;
        }

        /* Navigation Bar */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(15px);
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 18px 6%;
            z-index: 100;
            box-shadow: 0 4px 20px rgba(0, 43, 102, 0.05);
            border-bottom: 1px solid rgba(0, 85, 204, 0.1);
        }

        nav .logo {
            font-weight: 800;
            color: var(--blue-dark);
            font-size: 1.4rem;
            letter-spacing: 0.5px;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            color: var(--text-muted);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            font-size: 0.95rem;
        }

        nav a:hover {
            color: var(--blue-medium);
            transform: translateY(-2px);
        }

        /* Hero / Header Section */
        header {
            height: 90vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
            position: relative;
            background: linear-gradient(180deg, #ffffff 0%, #eef5fc 70%, #dbeafe 100%);
            overflow: hidden;
        }

        header h1 {
            font-size: 4rem;
            color: var(--blue-dark);
            margin-bottom: 25px;
            font-weight: 800;
            letter-spacing: -0.5px;
            z-index: 2;
        }

        header p {
            color: var(--blue-medium);
            font-size: 1.4rem;
            max-width: 800px;
            font-weight: 500;
            z-index: 2;
        }

        /* Trang trí đám mây trôi ở Header */
        .cloud-bg {
            position: absolute;
            background: rgba(255,255,255,0.7);
            border-radius: 100px;
            animation: floatCloud 25s infinite linear;
            z-index: 1;
        }
        @keyframes floatCloud {
            0% { transform: translateX(-200px); opacity: 0; }
            10%, 90% { opacity: 0.8; }
            100% { transform: translateX(1400px); opacity: 0; }
        }

        /* Sections */
        section {
            padding: 120px 8%;
            background-color: var(--bg-pure);
        }

        section:nth-child(even) {
            background: var(--bg-gradient);
        }

        h2 {
            color: var(--blue-dark);
            margin-bottom: 45px;
            font-size: 2.4rem;
            font-weight: 800;
            position: relative;
        }

        h2::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: -10px;
            width: 80px;
            height: 5px;
            background-color: var(--blue-medium);
            border-radius: 10px;
        }

        .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 70px;
            align-items: center;
        }

        .content-box {
            background: #ffffff;
            padding: 45px;
            border-radius: 16px;
            box-shadow: 0 20px 40px rgba(0, 43, 102, 0.04);
            border: 1px solid rgba(0, 85, 204, 0.08);
        }

        .content-box p {
            margin-bottom: 22px;
            font-size: 1.1rem;
            color: var(--text-main);
        }

        ul.steps li {
            margin-bottom: 20px;
            position: relative;
            padding-left: 32px;
            font-size: 1.1rem;
            list-style: none;
        }

        ul.steps li::before {
            content: "✦";
            position: absolute;
            left: 0;
            color: var(--blue-light);
            font-weight: bold;
            font-size: 1.2rem;
        }

        .example-box {
            background-color: var(--blue-tint);
            border-left: 5px solid var(--blue-medium);
            padding: 22px;
            border-radius: 4px 12px 12px 4px;
            margin-top: 30px;
            font-size: 1.05rem;
            color: var(--blue-dark);
        }

        /* --- PHẦN MINH HỌA SÁNG TẠO & ĐỘNG (CREATIVE VISUAL DISPLAYS) --- */
        .visual-display {
            background: #ffffff;
            height: 480px;
            border-radius: 20px;
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(0, 85, 204, 0.15);
            box-shadow: 0 25px 50px rgba(0, 43, 102, 0.08);
        }

        /* Nhãn chú thích kiểu hiện đại */
        .annotation {
            position: absolute;
            background: rgba(255, 255, 255, 0.95);
            color: var(--blue-dark);
            padding: 6px 12px;
            border-radius: 8px;
            font-size: 0.8rem;
            font-weight: 700;
            z-index: 30;
            border: 1px solid var(--blue-light);
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }

        /* 1. Đất Liền: Núi Non và Cắm Mốc Sinh Động */
        .scenery-land {
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, #e0f2fe 0%, #bae6fd 100%);
            position: relative;
        }

        .mountain-back {
            position: absolute;
            bottom: 0; width: 100%; height: 220px;
            background: #7dd3fc;
            clip-path: polygon(0% 100%, 15% 40%, 40% 75%, 65% 25%, 90% 70%, 100% 45%, 100% 100%);
            opacity: 0.7;
        }

        .mountain-front {
            position: absolute;
            bottom: 0; width: 100%; height: 160px;
            background: #38bdf8;
            clip-path: polygon(0% 100%, 25% 35%, 55% 65%, 80% 20%, 100% 60%, 100% 100%);
            z-index: 5;
        }

        .river-flow {
            position: absolute;
            bottom: 0; left: 45%; width: 90px; height: 110px;
            background: linear-gradient(to top, #0284c7, #38bdf8);
            clip-path: polygon(20% 0%, 80% 0%, 100% 100%, 0% 100%);
            z-index: 6;
        }

        .dynamic-marker {
            position: absolute;
            bottom: 60px; left: 50%;
            width: 16px; height: 55px;
            background: var(--accent-red);
            border: 3px solid #ffffff;
            border-radius: 2px;
            z-index: 10;
            box-shadow: 0 0 10px rgba(0,0,0,0.2);
            animation: landDrop 3s infinite alternate ease-in-out;
        }

        @keyframes landDrop {
            0% { transform: translateY(-80px) scale(0.9); opacity: 0; }
            60%, 100% { transform: translateY(0) scale(1); opacity: 1; }
        }

        /* 2. Trên Biển: Sóng Biển Trùng Điệp và Tàu Thuyền Hải Quân */
        .scenery-sea {
            width: 100%; height: 100%;
            background: linear-gradient(to bottom, #f0f9ff 0%, #e0f2fe 40%, #0284c7 100%);
            position: relative;
        }

        .ocean-waves-container {
            position: absolute;
            bottom: 0; width: 100%; height: 200px;
            z-index: 5;
        }

        /* Con thuyền tuần tra hải quân mượt mà */
        .navy-ship {
            position: absolute;
            bottom: 120px; left: 15%;
            width: 70px; height: 25px;
            background: #cbd5e1;
            clip-path: polygon(0% 40%, 85% 40%, 100% 0%, 85% 100%, 0% 100%);
            z-index: 8;
            animation: shipSway 4s infinite ease-in-out alternate;
        }
        .navy-ship::before {
            content: ''; position: absolute; top: -15px; left: 20px;
            width: 25px; height: 15px; background: #94a3b8;
        }

        @keyframes shipSway {
            0% { transform: translateY(0) rotate(0deg); }
            100% { transform: translateY(-8px) rotate(4deg); }
        }

        .eez-overlay-a {
            position: absolute; left: 0; top: 0; bottom: 0; width: 50%;
            background: linear-gradient(90deg, rgba(51,136,255,0.25), rgba(51,136,255,0.02));
            z-index: 2;
        }
        .eez-overlay-b {
            position: absolute; right: 0; top: 0; bottom: 0; width: 50%;
            background: linear-gradient(270deg, rgba(2,132,199,0.25), rgba(2,132,199,0.02));
            z-index: 2;
        }

        .center-law-line {
            position: absolute; left: 50%; top: 0; bottom: 0; width: 4px;
            background: var(--accent-red);
            box-shadow: 0 0 15px var(--accent-red);
            z-index: 10;
        }

        /* 3. Không Gian 3D: Vùng Trời Sinh Động Có Máy Bay Cất Cánh */
        .scenery-sky-space {
            width: 100%; height: 100%;
            display: flex; flex-direction: column;
            position: relative;
        }

        .sky-visual {
            height: 50%; background: linear-gradient(to bottom, #bae6fd 0%, #f0f9ff 100%);
            position: relative;
        }

        /* Giả lập máy bay chiến đấu bảo vệ không phận */
        .jet-plane {
            position: absolute; top: 30px; left: 10%;
            width: 45px; height: 15px;
            background: #64748b;
            clip-path: polygon(0% 50%, 40% 0%, 70% 50%, 100% 50%, 70% 100%, 40% 100%);
            animation: jetFly 6s infinite linear;
            z-index: 12;
        }

        @keyframes jetFly {
            0% { transform: translate(-50px, 60px) scale(0.7); opacity: 0; }
            15% { opacity: 1; }
            85% { opacity: 1; }
            100% { transform: translate(500px, -20px) scale(1.1); opacity: 0; }
        }

        .ground-divider {
            height: 12px; background: #475569; position: relative; z-index: 20;
        }

        .sub-earth-visual {
            height: 50%; background: linear-gradient(to bottom, #f1f5f9 0%, #cbd5e1 100%);
            position: relative;
        }

        .vertical-laser-plane {
            position: absolute; left: 50%; top: 0; bottom: 0; width: 3px;
            background: var(--accent-red);
            box-shadow: 0 0 12px rgba(255,77,77,0.9);
            z-index: 15;
        }

        .radar-glow {
            position: absolute; width: 100%; height: 4px;
            background: rgba(51, 136, 255, 0.6);
            box-shadow: 0 0 15px var(--blue-light);
            animation: radarGrid 4s infinite linear;
            z-index: 16;
        }

        @keyframes radarGrid {
            0% { top: 0%; }
            100% { top: 100%; }
        }

        /* Bảng tổng hợp dữ liệu */
        .table-wrapper {
            overflow-x: auto;
            margin-top: 50px;
            background: #ffffff;
            padding: 25px;
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(0, 43, 102, 0.03);
            border: 1px solid var(--blue-tint);
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            padding: 18px 24px;
            text-align: left;
            border-bottom: 1px solid var(--blue-tint);
        }

        th {
            background-color: var(--blue-tint);
            color: var(--blue-dark);
            font-weight: 700;
        }

        tr:hover {
            background-color: rgba(51, 136, 255, 0.03);
        }

        footer {
            text-align: center;
            padding: 60px;
            background: var(--blue-dark);
            color: #ffffff;
        }
    </style>
</head>
<body>

    <div class="cloud-bg" style="top: 15%; width: 120px; height: 40px; animation-duration: 28s;"></div>
    <div class="cloud-bg" style="top: 35%; width: 180px; height: 50px; animation-duration: 38s; animation-delay: -5s;"></div>

    <nav>
        <div class="logo">BIÊN GIỚI QUỐC GIA</div>
        <ul>
            <li><a href="#co-so-phap-ly">Cơ Sở Pháp Lý</a></li>
            <li><a href="#vùng-dat-lien">Biên Giới Trên Bộ</a></li>
            <li><a href="#vung-bien-dao">Biên Giới Trên Biển</a></li>
            <li><a href="#vung-troi-long-dat">Vùng Trời & Lòng Đất</a></li>
        </ul>
    </nav>

    <header>
        <h1>Phân Định Biên Giới Quốc Gia</h1>
        <p>Hệ thống danh mục nghiên cứu số hóa kết hợp đồ họa chuyển động trực quan sinh động</p>
    </header>

    <section id="co-so-phap-ly">
        <h2>I. Cơ Sở Pháp Lý Chung</h2>
        <div class="container">
            <div class="content-box">
                <p>Biên giới quốc gia cấu thành nên ranh giới phân định chủ quyền thiêng liêng độc lập của một đất nước với phần còn lại của thế giới.</p>
                <p>Hệ thống pháp luật tối cao dựa trên nền tảng <strong>Hiến chương Liên Hợp Quốc</strong>, khẳng định tính toàn vẹn lãnh thổ và kêu gọi giải quyết mọi tranh chấp ranh giới bằng thương lượng hòa bình.</p>
                <ul class="steps">
                    <li>Chủ quyền quốc gia là bất khả xâm phạm.</li>
                    <li>Sự kết hợp đồng bộ của cả 4 bộ phận không gian độc lập.</li>
                </ul>
            </div>
            <div class="visual-display" style="background: var(--blue-tint); display: flex; justify-content: center; align-items: center;">
                <div style="text-align: center; background: #ffffff; padding: 40px; border-radius: 20px; box-shadow: 0 15px 30px rgba(0,0,0,0.03); border: 2px solid var(--blue-light);">
                    <div style="font-size: 1.3rem; font-weight: 800; color: var(--blue-dark); margin-bottom: 20px;">4 KHÔNG GIAN RIÊNG BIỆT</div>
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 12px; font-weight: 700; color: var(--blue-medium);">
                        <div style="background: #f0fdf4; padding: 12px 20px; border-radius: 8px; border: 1px solid #bbf7d0;">⛰ Đất Liền</div>
                        <div style="background: #f0f9ff; padding: 12px 20px; border-radius: 8px; border: 1px solid #bae6fd;">🌊 Biển Khơi</div>
                        <div style="background: #fef2f2; padding: 12px 20px; border-radius: 8px; border: 1px solid #fecaca;">☁ Vùng Trời</div>
                        <div style="background: #fefaf0; padding: 12px 20px; border-radius: 8px; border: 1px solid #fed7aa;">💎 Lòng Đất</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="vùng-dat-lien">
        <h2>II. Quy Trình Xác Định Biên Giới Trên Bộ</h2>
        <div class="container">
            <div class="content-box">
                <p>Biên giới đất liền, đảo, sông hồ được thiết lập nghiêm ngặt qua 3 bước tiêu chuẩn:</p>
                <ul class="steps">
                    <li><strong>Bước 1: Hoạch định biên giới</strong> — Thương thảo, thống nhất và vẽ đường phân định pháp lý giả lập trên hệ thống bản đồ giấy.</li>
                    <li><strong>Bước 2: Phân giới thực địa</strong> — Đoàn chuyên viên trực tiếp khảo sát địa hình thực tế, đo đạc dòng chảy, ngọn núi để định hình tuyến biên giới ngoài đời thực.</li>
                    <li><strong>Bước 3: Cắm mốc giới</strong> — Tiền hành xây dựng các cột mốc bê tông/đá cố định và lập văn bản hồ sơ số hóa để quản lý quốc gia lâu dài.</li>
                </ul>
                <div class="example-box">
                    <strong>Thực tế cốt lõi:</strong> Việt Nam và Lào cùng khảo sát các rặng núi Trường Sơn, sau đó đồng loạt xây dựng hệ thống cột mốc đá hoa cương tại các tọa độ đỉnh đèo.
                </div>
            </div>
            <div class="visual-display">
                <div class="scenery-land">
                    <div class="mountain-back"></div>
                    <div class="mountain-front"></div>
                    <div class="river-flow"></div>
                    <div class="dynamic-marker"></div>

                    <div class="annotation" style="top: 25px; left: 25px;">Địa hình thực tế (Đèo / Núi cao)</div>
                    <div class="annotation" style="top: 150px; right: 30px;">Dòng chảy sông ngòi tự nhiên</div>
                    <div class="annotation" style="bottom: 140px; left: 35%;">Cột mốc được cắm tự động</div>
                </div>
            </div>
        </div>
    </section>

    <section id="vung-bien-dao">
        <h2>III. Quy Trình Phân Định Biên Giới Trên Biển</h2>
        <div class="container">
            <div class="content-box">
                <p>Khung phân định chủ quyền biển tuân thủ Công ước quốc tế <strong>UNCLOS 1982</strong>:</p>
                <ul class="steps">
                    <li><strong>Kịch bản không chồng lấn:</strong> Quốc gia sở hữu bờ biển hướng thẳng ra đại dương tự do vạch đường cơ sở và công bố vùng Lãnh hải rộng tối đa 12 hải lý.</li>
                    <li><strong>Kịch bản có vùng biển chồng lấn:</strong> Xảy ra khi khoảng cách bờ biển đối diện/liền kề giữa 2 nước hẹp (nhỏ hơn 400 hải lý). Hai bên bắt buộc phải ngồi vào bàn đàm phán ngoại giao, lấy <strong>Đường trung tuyến/Cách đều</strong> làm cơ sở tinh chỉnh để đạt giải pháp công bằng.</li>
                </ul>
            </div>
            <div class="visual-display">
                <div class="scenery-sea">
                    <div class="eez-overlay-a"></div>
                    <div class="eez-overlay-b"></div>
                    <div class="center-law-line"></div>
                    <div class="navy-ship"></div>

                    <div class="annotation" style="top: 30px; left: 20px;">Vùng biển thuộc Quốc gia A</div>
                    <div class="annotation" style="top: 30px; right: 20px;">Vùng biển thuộc Quốc gia B</div>
                    <div class="annotation" style="bottom: 160px; left: 28%;">Tàu tuần tra kiểm soát biển</div>
                    <div class="annotation" style="bottom: 30px; left: 40%; border-color: var(--accent-red);">Đường trung tuyến phân định</div>
                </div>
            </div>
        </div>
    </section>

    <section id="vung-troi-long-dat">
        <h2>IV & V. Cơ Chế Xác Định Vùng Trời & Lòng Đất</h2>
        <div class="container">
            <div class="content-box">
                <p>Không gian Không phận và Địa chất <strong>không được đo đạc phân định độc lập</strong>, mà phụ thuộc hoàn toàn vào đường ranh giới trên bề mặt đất và biển.</p>
                <ul class="steps">
                    <li><strong>Biên giới vùng trời (Công ước Chicago 1944):</strong> Là một bức tường mặt phẳng vô hình, dựng thẳng đứng từ mặt đất/mặt biển lên tận rìa bầu khí quyển.</li>
                    <li><strong>Biên giới lòng đất:</strong> Tương tự, là mặt phẳng vô hình kéo thẳng đứng xuyên qua các tầng địa chất hướng sâu về phía tâm Trái Đất.</li>
                </ul>
            </div>
            <div class="visual-display">
                <div class="scenery-sky-space">
                    <div class="sky-visual">
                        <div class="jet-plane"></div>
                    </div>
                    <div class="ground-divider"></div>
                    <div class="sub-earth-visual"></div>
                    
                    <div class="vertical-laser-plane"></div>
                    <div class="radar-glow"></div>

                    <div class="annotation" style="top: 25px; left: 15%;">Không phận (Chủ quyền bầu trời)</div>
                    <div class="annotation" style="top: 100px; right: 20%; border-color: var(--accent-red);">Mặt phẳng dựng đứng hướng thượng</div>
                    <div class="annotation" style="bottom: 30px; left: 15%;">Mỏ tài nguyên / Địa chất lòng đất</div>
                    <div class="annotation" style="bottom: 90px; right: 20%; border-color: var(--accent-red);">Mặt phẳng kéo thẳng xuống tâm</div>
                </div>
            </div>
        </div>
    </section>

    <section>
        <h2>VI. Khung Ma Trận Tổng Hợp Kiến Thức</h2>
        <div class="table-wrapper">
            <table>
                <thead>
                    <tr>
                        <th>Môi trường không gian</th>
                        <th>Bản chất quy trình phân định</th>
                        <th>Văn bản pháp lý nền tảng</th>
                        <th>Đặc trưng nhận diện trực quan</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Biên giới trên bộ</strong></td>
                        <td>Vẽ bản đồ → Khảo sát địa hình thực tế → Dựng cột mốc giới</td>
                        <td>Hiệp định song phương</td>
                        <td>Các cột mốc vật lý hiện hữu ngoài thực địa</td>
                    </tr>
                    <tr>
                        <td><strong>Biên giới trên biển</strong></td>
                        <td>Thiết lập đường cơ sở pháp lý, tính hải lý hoặc đàm phán chồng lấn</td>
                        <td>UNCLOS 1982</td>
                        <td>Áp dụng nguyên tắc đường cách đều/trung tuyến</td>
                    </tr>
                    <tr>
                        <td><strong>Biên giới vùng trời</strong></td>
                        <td>Hình chiếu hình học thẳng đứng từ ranh giới đất/biển lên không trung</td>
                        <td>Công ước Chicago 1944</td>
                        <td>Bức tường vô hình bao trọn không phận quốc gia</td>
                    </tr>
                    <tr>
                        <td><strong>Biên giới lòng đất</strong></td>
                        <td>Hình chiếu hình học thẳng đứng từ ranh giới đất/biển sâu xuống lòng đất</td>
                        <td>Luật Biên giới Quốc gia</td>
                        <td>Xác định quyền khai thác tài nguyên dầu khí, khoáng sản</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </section>

    <footer>
        <p>© 2026 Nghiên Cứu Số Hóa Luật Quốc Tế — Thiết kế sáng tạo đồ họa trực quan</p>
    </footer>

</body>
</html>]" > index.html

# Push to GitHub
git add index.html
git commit -m "Initial commit: Create portfolio website on national boundary demarcation"
git push origin main
