<script>

    import { onMount } from "svelte";

    var map;
    onMount(() => {
        init_map();
    });

    map = new L.Map("map", { center: [52.0919, 5.09], zoom: 8, attributionControl: false, scrollWheelZoom: true, zoomControl: false, zoomAnimation: false });
    function init_map() {
        L.tileLayer('https://service.pdok.nl/brt/achtergrondkaart/wmts/v2_0/grijs/EPSG:3857/{z}/{x}/{y}.png', {maxZoom: 18}).addTo(map);
        map.pm.addControls({ drawMarker: false, drawPolygon: true, editMode: false, drawPolyline: false, removalMode: true, });
    }
    
</script>