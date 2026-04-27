# Oreretako-ahotsak

<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mi mapa</title>
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"/>
  <style>
    body { margin: 0; }
    #map { height: 100vh; width: 100%; }
  </style>
</head>
<body>
  <div id="map"></div>
  <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
  <script>
    // Centro del mapa: coordenadas de San Sebastián
    const map = L.map('map').setView([43.3183, -1.9812], 13);

    // Capa de tiles (OpenStreetMap, gratuito)
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '© OpenStreetMap contributors'
    }).addTo(map);

    // Marcador de ejemplo
    L.marker([43.3183, -1.9812])
      .addTo(map)
      .bindPopup('<b>Donostia</b><br>¡Hola desde aquí!')
      .openPopup();
  </script>
</body>
</html>
const lugares = [
  { coords: [43.3183, -1.9812], nombre: "Donostia" },
  { coords: [43.2630, -2.9349], nombre: "Bilbao" },
  { coords: [42.8467, -2.6716], nombre: "Vitoria" },
];

lugares.forEach(({ coords, nombre }) => {
  L.marker(coords).addTo(map).bindPopup(nombre);
});
