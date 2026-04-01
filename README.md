# Portal de Firmas - Ranking Online

Este proyecto contiene el código fuente de una herramienta interna para generar, previsualizar y exportar las firmas de correo electrónico corporativas del equipo de **Ranking Online**. 

Se ha desarrollado teniendo en mente el complejo ecosistema de motores de renderizado de clientes de correo (Outlook, Gmail, Mail), por lo que las firmas se basan estrictamente en disposiciones por tablas garantizando 100% de compatibilidad.

## Funcionalidades del Dashboard interactivo
- **Vista Previa en Tiempo Real:** Visualiza cómo se verá la firma terminada antes de instalarla en diferentes dispositivos.
- **Variante 1**: Diseño horizontal con datos a la izquierda sin fotografía.
- **Variante 2**: Diseño ampliado con foto personal circular y logotipos apilados a la izquierda.
- **Interruptor para Redes Sociales**: Configuración para apagar o encender el componente interactivo de los perfiles sociales en vivo.
- **Extractor HTML "Limpiador"**: Un modal extrae el código, borra temporalidades y facilita su volcado exacto (`Copiar Portapapeles`) listo para pegarse en configuraciones de firmas.

## 🛠 Modo de Implementación de la Firma
Los correos electrónicos **requieren referenciar imágenes de servidores públicos**.

Para instalar oficialmente estas firmas en un usuario, los desarrolladores/managers deben:
1. Subir a su propio hosting, AWS S3 o CDN toda la carpeta `/assets` del repositorio (para exponer públicamente el `picture-person.png`, iconografía `.svg` y los logotipos de RO).
2. Hacer un *Buscar y Reemplazar* de forma simple dentro del archivo `index.html`, sustituyendo cualquier ruta `src="assets/...` hacia la ruta online definitiva (Ej: `src="https://rankingonline.com/...`).
3. Posterior al reemplazo, solo hay que abrir `index.html` en Chrome, usar la Variante deseada, presionar el botón de **Copiar HTML**, y pegar dicho código limpio en los ajustes de firma de Gmail o Outlook.
