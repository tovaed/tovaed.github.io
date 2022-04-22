<meta charset="utf-8">
<link href="desincriptador.css" rel="stylesheet" type="text/css">
<head></head>
<body>
	<div id="contenedor">
		<div id="entrada">
			<img src="Vector.png" id="logo">
			<br>
			<h1>Programa para encriptar y desencriptar</h1>

			<textarea type="text" placeholder="Ingrese aquí su texto" id="texto"></textarea>	

			<!-- Botones de acción -->
			<button id="encripta" onclick="codifica()">Encriptar</button>
			<button id="desencripta" onclick="descodifica()">Desencriptar</button>

			<p>Recuerda NO puedes usar mayusculas ni acentos</p>
		</div>

		<div id="salida">
			<img src="Muñeco.png">

			<b><p>No ha ingresado ningún texto</p></b>
			<p>Ingrese un texto para encriptar o desencriptar</p>
		</div>

		<div id="salida2">
			<p>Su resultado fue</p>
			<p id="escrito" ></p>
			<button id="copiar" onclick="copiar()">Copiar</button>
		</div>
	</div>
	<script>

		function codifica() 
		{
  			var x = document.getElementById('salida');
  			
  			if (x.style.display === 'none') 
  			{
    			x.style.display = 'block';
    			
  			} else {
    			x.style.display = 'none';
  			}

  			var texto = document.getElementById("texto").value;

  			var cadena = texto;
  			var arreglo = [];
  			arreglo = cadena.split("");
  			for (var i = 0; i < arreglo.length; i++) {
  				if (arreglo[i] == "a") 
  				{
  					arreglo[i] = "ai";

  				}
  				if (arreglo[i] == "e") 
  				{
  					arreglo[i] = "enter";

  				}
  				if (arreglo[i] == "i") 
  				{
  					arreglo[i] = "imes";

  				}
  				if (arreglo[i] == "o") 
  				{
  					arreglo[i] = "ober";

  				}
  				if (arreglo[i] == "u") 
  				{
  					arreglo[i] = "ufat";

  				}
  				console.log(arreglo[i]);
  				var codigo = arreglo.join("");
  				document.getElementById("escrito").innerHTML = codigo;
  			}

  			
  		}

  		function descodifica() 
		{
  			var x = document.getElementById('salida');
  			
  			if (x.style.display === 'none') 
  			{
    			x.style.display = 'block';
    			
  			} else {
    			x.style.display = 'none';
  			}

  			var texto = document.getElementById("texto").value;
  			//document.getElementById("escrito").innerHTML = "Su texto descodificado es: "+texto;
  			var cadena = texto;
  			arreglo = cadena.split(" ");
  			cadena = cadena.replace(/ai/g,"a");
  			cadena = cadena.replace(/enter/g,"e");
  			cadena = cadena.replace(/imes/g,"i");
  			cadena = cadena.replace(/ober/g,"o");
  			cadena = cadena.replace(/ufat/g,"u");
  			console.log(cadena);
  			document.getElementById("escrito").innerHTML = cadena;
  		}

  		function copiar()
  		{
  			var aux = document.createElement("input");
            aux.setAttribute("value", document.getElementById("escrito").innerHTML);
            document.body.appendChild(aux);
            aux.select();
            document.execCommand("copy");
            document.body.removeChild(aux);
  		}		
</script>
</body>
