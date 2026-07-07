# Casino Frontend

Frontend del casino online, construido con Angular 17.

## Construir (Build)
Para instalar las dependencias:
```bash
npm install
```
Para construir la aplicación para producción:
```bash
npm run build
```

## Probar (Test)
Para ejecutar las pruebas unitarias usando Karma/Jasmine:
```bash
npm test -- --watch=false --browsers=ChromeHeadless
```

## Desplegar (Deploy)
El despliegue está automatizado con GitHub Actions en la rama `deploy`.
Flujo automatizado: Build -> Test -> Push a ECR -> Deploy a EKS.

Para despliegue local en Kubernetes:
```bash
kubectl apply -f ../k8s/frontend.yaml
```

## Troubleshooting
- **Error 404 o página en blanco**: Asegúrate de que el LoadBalancer está enrutando correctamente el tráfico (`kubectl get svc frontend`).
- **Fallo en CI/CD**: Verifica la pestaña de GitHub Actions para ver si el test de Karma falló o faltó configuración en `angular.json`.
