<script>
  const domParser = new DOMParser();

  export let data = ''
  export let viewBox = '0 0 20 20'
  
  export let size = '20px'
  export let width = size
  export let height = size

  export let color = 'currentColor'
  export let stroke = color
  export let fill = color

  let elements;

  $: {
    const svgDom = domParser.parseFromString(data, 'image/svg+xml').firstChild;
    viewBox = svgDom.getAttribute('viewBox');
    elements = svgDom.innerHTML;
  }
</script>

<svg
  xmlns="http://www.w3.org/2000/svg"
  {width}
  {height}
  {viewBox}
  {stroke}
  {fill}
>
  {@html elements}
</svg>
