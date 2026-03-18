<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Los Detectives de la Oración</title>
    <style>
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background-color: #f0f4f8; color: #333; line-height: 1.6; padding: 20px; }
        .container { max-width: 800px; margin: auto; background: white; padding: 30px; border-radius: 12px; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }
        h1 { color: #2c3e50; text-align: center; border-bottom: 2px solid #3498db; padding-bottom: 10px; }
        .instrucciones { background: #e8f4fd; padding: 15px; border-radius: 8px; margin-bottom: 20px; }
        .reto-box { margin-bottom: 25px; padding: 20px; border: 1px solid #ddd; border-radius: 8px; }
        .oracion { font-size: 1.4em; font-weight: bold; color: #e67e22; margin-bottom: 15px; display: block; }
        select, input { padding: 8px; font-size: 1em; border-radius: 4px; border: 1px solid #ccc; width: 100%; margin-top: 5px; }
        button { background-color: #27ae60; color: white; border: none; padding: 10px 20px; border-radius: 5px; cursor: pointer; font-size: 1em; margin-top: 10px; transition: 0.3s; }
        button:hover { background-color: #219150; }
        .feedback { margin-top: 10px; font-weight: bold; }
        .success { color: #27ae60; }
        .error { color: #e74c3c; }
    </style>
</head>
<body>

<div class="container">
    <h1>🔍 Misión: Los Detectives de las Oraciones</h1>
    
    <div class="instrucciones">
        <p><strong>Instrucciones:</strong> Analiza la siguiente oración y selecciona la función sintáctica correcta para la parte subrayada.</p>
    </div>

    <div id="juego">
        <div class="reto-box">
            <span class="oracion">El detective <span style="text-decoration: underline;">encontró las pistas</span> en el jardín.</span>
            <label for="opcion1">¿Cuál es el Predicado?</label>
            <select id="pregunta1">
                <option value="">-- Elige una opción --</option>
                <option value="sujeto">El detective</option>
                <option value="predicado">encontró las pistas en el jardín</option>
                <option value="cd">las pistas</option>
            </select>
            <button onclick="verificar()">Comprobar Misión</button>
            <div id="feedback" class="feedback"></div>
        </div>
    </div>
</div>

<script>
    function verificar() {
        const respuesta = document.getElementById('pregunta1').value;
        const feedback = document.getElementById('feedback');
        
        if (respuesta === "predicado") {
            feedback.innerHTML = "✅ ¡Excelente trabajo, detective! Has identificado el Predicado correctamente.";
            feedback.className = "feedback success";
        } else if (respuesta === "") {
            feedback.innerHTML = "⚠️ Por favor, selecciona una respuesta.";
            feedback.className = "feedback";
        } else {
            feedback.innerHTML = "❌ ¡Oh no! Esa pista es falsa. Inténtalo de nuevo.";
            feedback.className = "feedback error";
        }
    }
</script>

</body>
</html>
