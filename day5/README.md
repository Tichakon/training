# Traning Modernize Day 5

- Remote เข้าไปใช้งาน Docker บนเซิฟเวอร์

## Solve
- ปกติการลง Docker Desktop ใช้สำหรับการ Training เท่านั้น เพื่อความง่ายแตะติดตั้งได้ไว ปัจจุบัน Docker Desktop มีเรื่องข้อจำกัดเรื่อง License ทำให้ในอนาคตอาจจะไม่สามารถใช้งานได้
- ควบคุม Docker ที่อยู่บนเซิฟเวอร์อื่น
- OS ใช้ไม่เหมือนกัน ถ้าย้ายมาใช้ Docker บนเซิฟเวอร์แทนคิดว่าปัญหาน่าจะน้อยลง

## Tools
- [Portainer](https://www.portainer.io/)
- [code-server](https://code.visualstudio.com/docs/remote/vscode-server)

## Run portainer
```
docker run -d -p 8000:8000 -p 9443:9443 -p 9000:9000 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```

## Tools อื่น ๆ ที่ใช้แทน Docker Desktop
- [Rancher](https://www.rancher.com/)
- [Minikube](https://minikube.sigs.k8s.io/docs/)
- [Podman](https://podman.io/)

## Ref
- https://docs.docker.com/engine/install/ubuntu/
- https://www.portainer.io/
- https://github.com/portainer/portainer
- https://github.com/coder/code-server
- https://blog.tichaky.com/use-portainer-to-manage-containers/ (ในนี้จะไม่มีการเพิ่ม -p 9000:9000 แต่ของใหม่ต้องใช้สำหรับรัน http)