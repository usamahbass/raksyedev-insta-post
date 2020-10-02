<!-- Spread.svelte -->

<script>
	export let name ;
	export let age;
	export let url;
</script>

<p>
    Hello this is {name}.
    <br/> 
    The person behind this is aged {age} , 
    visit my web at <a href={url}>{url}</a>
</p>