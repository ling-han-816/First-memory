<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body { 
      font-family: Arial, sans-serif; 
      background: linear-gradient(to right, #5B5B5B, #8E8E8E); /* 加入漸層背景 */
      color: #3C3C3C;
      margin: 0; /* 移除預設邊距 */
      height: 100vh; /* 設置頁面高度 */
      overflow: hidden; /* 隱藏滾動條 */
      transition: background 0.5s ease; /* 平滑背景轉換 */ 
    }

    /* 主要容器 */
    .main-container {
      display: flex;
      flex-direction: column; /* 垂直排列 */
      align-items: center; /* 水平置中 */
      margin: 20px; /* 外邊距 */
      height: 100%; /* 讓容器也填滿頁面 */
      justify-content: center;
    }

    /* 音樂播放器容器 */
    .audio-container {
      margin: 10px 0; /* 縮小上下邊距 */
    }

    /* 照片容器 */
    .photo-container {
      display: flex;
      justify-content: center;
      margin: 10px 0; /* 縮小上下邊距 */
    }

    /* 歌名和團名 */
    .song-info {
      font-size: 20px; /* 字體大小 */
      color: #222; /* 字體顏色 */
      margin: 4px 0; /* 調整間距 */
      text-align: center; /* 文字置中 */
      font-weight: bold; /* 設置為粗體 */
    }

    /* 歌詞容器 */
    .lyrics-container {
      margin: 20px auto;
      height: 165px;
      width: 80%;
      overflow-y: scroll;
      text-align: center;
    }

    .lyrics-container::-webkit-scrollbar {
      display: none; /* 隱藏滾動條 */
    }

    .lyrics-container {
      scrollbar-width: none; /* 隱藏 Firefox 的滾動條 */
    }

    .lyrics p {
      margin: 5px 0;
      font-size: 18px;
      line-height: 1.5;
      color: #3C3C3C;
    }

    .lyrics p.active {
      color: #fff;
      font-weight: bold;
    }

    /* 照片樣式 */
    .photo {
      width: 45%; /* 照片寬度，根據需要調整 */
      border-radius: 10px; /* 圓角邊框，根據需要調整 */
    }

    /* 背景上傳按鈕樣式 */
    .upload-container {
      margin-top: 20px;
      text-align: center;
    }
  </style>
  <title>姚曉棠&張新成_最初的記憶</title>
</head>
<body>
  <div class="main-container">
    <!-- 添加圖片 -->
    <div class="photo-container">
      <img src="S__14377005.jpg" alt="Song Image" class="photo"> <!-- 在這裡替換成你的圖片路徑 -->
    </div>

    <!-- 歌名和團名 -->
    <div class="song-info">最初的記憶 - 姚曉棠&張新成</div>
    
    <!-- 第一首歌 -->
    <div class="audio-container">
      <audio id="audio4" controls>
        <source src="最初的記憶.mp3" type="audio/mp3"> <!-- 第一首歌音檔 -->
      </audio>
    </div>
    
    <!-- 歌詞顯示區域 -->
    <div class="lyrics-container" id="lyrics-container4">
      <div class="lyrics" id="lyrics4">
        <p data-time="8.5">雨過天晴之后的天</p>
        <p data-time="14.8">有一點不浪漫感覺</p>
        <p data-time="22.5">一直到彩虹出現那天</p>
        <p data-time="28.6">這一刻才發現 再想一次之前</p>
        <p data-time="36.5">明明知道你會走遠 我還是拼命靠前</p>
        <p data-time="50.9">才懂到明白你已經不見</p>
        <p data-time="56.5">我還不能妥協</p>
        <p data-time="64.3">我很安靜陪著你 有些懷疑</p>
        <p data-time="72.5">能不能陪我到最終目的</p>
        <p data-time="78.5">我的安靜不懷疑 就別再提</p>
        <p data-time="87">能不能讓我回到最初的記憶</p>
        <p data-time="107.1">明明知道你會走遠</p>
        <p data-time="113.3">我還是拼命靠前</p>
        <p data-time="121.1">才懂到明白你已經不見</p>
        <p data-time="127.4">我還不能妥協</p>
        <p data-time="134.9">我很安靜陪著你</p>
        <p data-time="139.9">有些懷疑</p>
        <p data-time="143.3">能不能陪我到最終目的</p>
        <p data-time="148.9">我的安靜不懷疑</p>
        <p data-time="153.9">就別再提</p>
        <p data-time="157.5">能不能讓我回到最初的記憶</p>
        <p data-time="166.9">一直到最后都我還相信你</p>
        <p data-time="170.5">才明白這一切都只是曾經</p>
        <p data-time="174.1">我的心陪著你把自己關緊</p>
        <p data-time="181.2">不要說你還在我不會相信</p>
        <p data-time="184.7">只好等所有的情緒都穩定</p>
        <p data-time="187.9">愛情本來就想起</p>
        <p data-time="195">我很安靜陪著你 有些懷疑</p>
        <p data-time="203.2">能不能陪我 到最終目的</p>
        <p data-time="208.9">我很安靜不懷疑就別再提</p>
        <p data-time="217.2">我只想讓你回到最初的記憶</p>
      </div>
    </div>

    <!-- 背景圖片上傳 -->
    <div class="upload-container">
      <label for="bgUpload">可以自訂背景呦</label>
      <input type="file" id="bgUpload" accept="image/*">
    </div>
  </div>

<script>
    // 背景上傳處理邏輯
    const bgUpload = document.getElementById('bgUpload');
    bgUpload.addEventListener('change', function (event) {
      const file = event.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function (e) {
          document.body.style.backgroundImage = `url(${e.target.result})`;
          document.body.style.backgroundSize = 'cover';  // 背景圖片覆蓋整個頁面
          document.body.style.backgroundPosition = 'center';  // 圖片置中
          document.body.style.backgroundRepeat = 'no-repeat';  // 圖片不重複
        };
        reader.readAsDataURL(file); // 讀取上傳的圖片
      }
    });

    // 歌詞同步功能
    function syncLyrics(audio, lyricsElement, containerElement) {
      const lyrics = lyricsElement.getElementsByTagName('p');
      
      audio.addEventListener('timeupdate', () => {
        for (let i = 0; i < lyrics.length; i++) {
          const time = parseFloat(lyrics[i].getAttribute('data-time'));
          const nextTime = lyrics[i + 1] ? parseFloat(lyrics[i + 1].getAttribute('data-time')) : Infinity;

          if (audio.currentTime >= time && audio.currentTime < nextTime) {
            lyrics[i].classList.add('active'); // 當前歌詞變為活躍
            lyrics[i].scrollIntoView({ behavior: 'smooth', block: 'center' }); // 自動滾動並將當前歌詞居中
          } else {
            lyrics[i].classList.remove('active');
          }
        }
      });
    }

    // 對每首歌進行歌詞同步
    const audio4 = document.getElementById('audio4');
    const lyrics4 = document.getElementById('lyrics4');
    const container4 = document.getElementById('lyrics-container4');
    syncLyrics(audio4, lyrics4, container4);
  </script>

</body>
</html>
