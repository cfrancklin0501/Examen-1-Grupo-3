# Examen Docker — David Joel Rivas Ortega

Esta carpeta cumple la estructura exacta del examen y trae **scripts opcionales** `run.sh` para llenar automáticamente los `comandos.txt` con salidas reales.

## Estructura
```
david-joel-rivas-ortega-examen/
├── parte1/
│   ├── comandos.txt      # comandos y script opcional para evidencias
│   └── run.sh            # (opcional) llena comandos.txt con salidas reales
├── parte2/
│   ├── Dockerfile
│   ├── app.py
│   ├── requirements.txt
│   ├── .dockerignore
│   ├── comandos.txt
│   └── run.sh            # (opcional) construye, corre, prueba y documenta
└── parte3/
    ├── docker-compose.yml
    ├── api/
    │   ├── Dockerfile    # multi-stage (punto extra)
    │   ├── server.js
    │   └── package.json
    ├── web/
    │   └── index.html
    ├── comandos.txt
    └── run.sh            # (opcional) levanta, prueba, logs y limpia
```

## Requisitos previos
- Docker y Docker Compose instalados
- `curl` disponible para pruebas HTTP
- Puertos **3000**, **5000**, **8080** libres (y **8081** si usas Mongo Express)

## Pasos rápidos
### Parte 1 (CLI)
```bash
cd parte1
bash run.sh     # o copia/pega desde comandos.txt
```

### Parte 2 (Dockerfile + Flask)
```bash
cd parte2
bash run.sh     # construye, ejecuta, prueba y documenta
```

### Parte 3 (Compose: API+Web+DB)
```bash
cd parte3
bash run.sh     # levanta el stack, prueba, logs y down -v
```

## Puntos extra incluidos
- Parte 2: **HEALTHCHECK** en el Dockerfile (+0.5)
- Parte 3: API con **multi-stage build** en `api/Dockerfile` (+0.5)
- Parte 3: Servicio **Mongo Express** opcional en `docker-compose.yml` (+0.5)
- Este `README.md` con instrucciones claras (+0.5)

> Si tu docente no desea servicios extra, no hay problema: el `docker-compose.yml` funciona igual con `api`, `web` y `db`; `mongo-express` es opcional.

---

**Nota:** Los scripts `run.sh` generan y/o enriquecen `comandos.txt` con **salidas reales** (logs, IP, `curl`, etc.).
