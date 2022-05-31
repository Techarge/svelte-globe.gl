<script lang="ts">
    import Globe from 'globe.gl';
    import {onMount} from "svelte";

    export let name: String = "component";
    const N: number = 300;
    const gData = [...Array(N).keys()].map(() => ({
      lat: (Math.random() - 0.5) * 180,
      lng: (Math.random() - 0.5) * 360,
      size: Math.random() / 3,
      color: ['red', 'white', 'blue', 'green'][Math.round(Math.random() * 3)]
    }));

    onMount(() => {
        Globe()
      .globeImageUrl('//unpkg.com/three-globe/example/img/earth-night.jpg')
      .pointsData(gData)
      .pointAltitude('size')
      .pointColor('color')
    (document.getElementById('globeViz'))
    })

</script>

<h1>Hello {name}</h1>
<div id="globeViz"></div>
