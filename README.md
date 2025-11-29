[杨炼标的第三次作业.html](https://github.com/user-attachments/files/23816435/default.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title></title>
    <style>
        
        .carousel {
            width: 500px;  
            height: 300px;
            margin: 0 auto;
            position: relative;
            overflow: hidden;
            border: 1px solid #eee;
        }
        
        .carousel-imgs {
            display: flex;
            width: 100%;
            height: 100%;
            transition: transform 0.5s ease; 
        }
        
        .carousel-img {
            width: 100%;
            height: 100%;
            object-fit: cover; 
            flex: 0 0 auto; 
        }
     
        .carousel-btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            width: 40px;
            height: 40px;
            background: rgba(0,0,0,0.5);
            color: white;
            border: none;
            cursor: pointer;
            font-size: 20px;
            z-index: 10; 
        }
        .prev-btn { left: 10px; }
        .next-btn { right: 10px; }
        
        .carousel-dots {
            position: absolute;
            bottom: 15px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 8px;
            z-index: 10;
        }
        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(255,255,255,0.5);
            cursor: pointer;
        }
        
        .dot.active {
            background: white;
        }
    </style>
</head>
<body>
    <div class="carousel">
        <div class="carousel-imgs">
            <img src="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214932_92_41.jpg" class="carousel-img" alt="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214932_92_41.jpg">
            <img src="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214930_91_41.jpg" class="carousel-img" alt="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214930_91_41.jpg">
            <img src="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214934_93_41.jpg" class="carousel-img" alt="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214934_93_41.jpg">
            <img src="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214936_95_41.jpg" class="carousel-img" alt="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214936_95_41.jpg">
            <img src= "C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214942_97_41.jpg" class="carousel-img" alt="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214942_97_41.jpg">
            <img src="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214945_98_41.jpg" class="carousel-img" alt="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214945_98_41.jpg">
            <img src="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214946_99_41.jpg" class="carousel-img" alt="C:\Users\杨练标\Pictures\Saved Pictures\微信图片_20251028214946_99_41.jpg">
        </div>
    
        <button class="carousel-btn prev-btn">&lt;</button>
        <button class="carousel-btn next-btn">&gt;</button>
       
        <div class="carousel-dots">
            <div class="dot active"></div>
             <div class="dot"></div>
            <div class="dot"></div>
             <div class="dot"></div>
             <div class="dot"></div>
            <div class="dot"></div>
            <div class="dot"></div>
        </div>
    </div>

    <script>
       
        const imgsContainer = document.querySelector('.carousel-imgs'); 
        const imgs = document.querySelectorAll('.carousel-img'); 
        const prevBtn = document.querySelector('.prev-btn'); 
        const nextBtn = document.querySelector('.next-btn'); 
        const dots = document.querySelectorAll('.dot'); 

        let currentIndex = 0; 
        const imgWidth = imgs[0].offsetWidth;

        
        function goToIndex(index) {
           
            if (index < 0) index = imgs.length - 1;
            if (index >= imgs.length) index = 0;
            
            
            imgsContainer.style.transform = `translateX(-${index * imgWidth}px)`;
            
            
            dots.forEach((dot, i) => {
                dot.classList.toggle('active', i === index);
            });
            
           
            currentIndex = index;
        }

        
        prevBtn.addEventListener('click', () => goToIndex(currentIndex - 1)); 
        nextBtn.addEventListener('click', () => goToIndex(currentIndex + 1)); 

       
        dots.forEach((dot, index) => {
            dot.addEventListener('click', () => goToIndex(index));
        });

        
        setInterval(() => {
            goToIndex(currentIndex + 1);
        }, 3000);
    </script>
</body>
</html>
![微信图片_20251028214932_92_41](https://github.com/user-attachments/assets/d75a829c-b698-420b-985d-4957f5b7de12)


