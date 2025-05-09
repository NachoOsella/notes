### 🧪 **Trabajo con ramas en Git – Mini resumen**

1. **Crear y moverse a una nueva rama:**
    
    ```bash
    git checkout -b nombre-rama
    ```
    
2. **Hacer cambios y commitear como siempre:**
    
    ```bash
    git add .
    git commit -m "mensaje"
    ```
    
3. **Subir la rama al remoto (sin tocar main):**
    
    ```bash
    git push -u origin nombre-rama
    ```
    
4. **Moverse entre ramas:**
    
    ```bash
    git checkout nombre-rama  # una opcion
    git switch nombre-rama    # otra opcion
    ```
    
5. **Ver ramas locales:**
    ```bash
    git branch
    ```