<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>生日祝福墙</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background: linear-gradient(120deg, #ff9a9e, #fad0c4);
            color: white;
            overflow: hidden;
        }
        h1 {
            font-size: 3em;
            text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.3);
        }
        .container {
            margin-top: 20px;
        }
        input, textarea, button {
            width: 80%;
            padding: 10px;
            margin: 10px;
            border-radius: 5px;
            border: none;
        }
        button {
            background: #ff4b5c;
            color: white;
            font-size: 1.2em;
            cursor: pointer;
        }
        .messages {
            margin-top: 20px;
            text-align: left;
            width: 80%;
            margin: auto;
        }
        .message {
            background: white;
            color: black;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
        }
        .balloons {
            position: fixed;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            z-index: -1;
        }
    </style>
</head>
<body>
    <h1>🎂 生日祝福墙 🎂</h1>
    <div class="container">
        <input id="name" placeholder="你的名字">
        <textarea id="message" placeholder="你的祝福"></textarea>
        <button onclick="sendMessage()">提交留言</button>
        <div class="messages" id="messages"></div>
    </div>
    <audio autoplay loop>
        <source src="happy-birthday.mp3" type="audio/mpeg">
    </audio>
    <script>
        function sendMessage() {
            const name = document.getElementById('name').value;
            const message = document.getElementById('message').value;
            if (!name || !message) {
                alert("请输入姓名和祝福语！");
                return;
            }
            const msgDiv = document.createElement("div");
            msgDiv.className = "message";
            msgDiv.innerHTML = `<strong>${name}:</strong> ${message}`;
            document.getElementById("messages").appendChild(msgDiv);
            document.getElementById('name').value = "";
            document.getElementById('message').value = "";
        }
    </script>
</body>
</html>
