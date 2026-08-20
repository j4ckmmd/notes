Login con Google Cloud
```sh
gcloud auth login
```

Setear proyecto
```sh
gcloud config set project datta-app-dev
```

Ver mi cuenta autenticada
```sh
gcloud auth list
```

Crear una imagen con un GITHUB_TOKEN temporal
```sh
docker build --secret id=github_token,env=GITHUB_TOKEN -t {image_name}:{tag_name} .
```

Tagear una imagen para subirlo a un repo de Artifact Registry
```sh
docker tag {image_name}:{tag_name} {region}-docker-pkg.dev/{project_id}/{repo_id}/{tag_name}
```

Subir imagen
```sh
docker push {image_name}
```
