🚀 Containerized Flask App on AWS (ECS + ECR)
🏗️ 1. Architecture Overview (START HERE)

📸 Take screenshot of your architecture diagram (draw.io / AWS icons / hand-drawn AWS flow)
<img width="1536" height="1024" alt="ChatGPT Image Jun 21, 2026, 05_24_07 PM" src="https://github.com/user-attachments/assets/97e0befe-fb43-4e47-9d58-3fef30b5c80d" />


Flow:

Flask App → Docker → ECR → ECS → Load Balancer → User

🐳 2. Docker Image Build (Local Machine)

📸 Screenshot: terminal showing docker build
<img width="1272" height="807" alt="build docker image" src="https://github.com/user-attachments/assets/a477251e-c692-442f-b5df-b90b6be8081f" />


docker build -t flask-app .
▶️ 3. Run Container Locally (Validation Step)

📸 Screenshot: browser showing localhost OR terminal running container

<img width="1816" height="707" alt="running container broweser" src="https://github.com/user-attachments/assets/faa441d7-3deb-45f0-bb01-dcccebd100a3" />

docker run -p 5000:5000 flask-app
☁️ 4. Amazon ECR Repository Creation

📸 Screenshot: AWS Console → ECR → Create repository
<img width="1912" height="732" alt="Screenshot 2026-06-21 173848" src="https://github.com/user-attachments/assets/c21f38ba-4aa0-4f50-a011-03e467d478ef" />


📦 5. Docker Image Push to ECR

📸 Screenshot: terminal showing login + push

<img width="1452" height="441" alt="Screenshot 2026-06-21 173946" src="https://github.com/user-attachments/assets/899e3825-870d-4d33-af33-2b10210ff3ab" />

aws ecr get-login-password | docker login ...
docker tag flask-app:latest <repo-uri>
docker push <repo-uri>
🗂️ 6. ECR Repository (Image Stored)

📸 Screenshot: AWS ECR showing uploaded image
<img width="1421" height="726" alt="Screenshot 2026-06-21 174233" src="https://github.com/user-attachments/assets/8bb3adb7-729a-4d7e-a854-6b8bb524381d" />


🚀 7. ECS Cluster Creation

📸 Screenshot: ECS cluster dashboard
<img width="1918" height="640" alt="Screenshot 2026-06-21 174341" src="https://github.com/user-attachments/assets/224f000f-b1b6-4dd1-9feb-f5a1e502f89b" />


📄 8. ECS Task Definition Setup

📸 Screenshot: task definition page (container image from ECR)
<img width="1877" height="768" alt="Screenshot 2026-06-21 174549" src="https://github.com/user-attachments/assets/feda5564-1c81-47f8-a6bc-92b67ac8782f" />


⚙️ 9. ECS Service Running

📸 Screenshot: running tasks = 1/1 healthy
<img width="1912" height="780" alt="Screenshot 2026-06-21 174730" src="https://github.com/user-attachments/assets/ec09df53-e6a8-481e-a399-90aefc276769" />


🌐 10. Load Balancer / Public URL Access

📸 Screenshot: browser showing Flask app live
<img width="1816" height="707" alt="Screenshot 2026-06-21 161419" src="https://github.com/user-attachments/assets/44135c93-7ee8-4801-8a82-7245b543a1cd" />

live demo:
http://13.206.73.13:5000/
