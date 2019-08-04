<script>
	import { onMount } from 'svelte';
	
	const list  = []
	for(let i = 0; i < 50000; i++) {
		list.push(i);
    }
    let time = new Date();
	const beginTime = +new Date();
	let name = 'world';
	let data = new Array(50000)
	function click(index){
		return ()=> {
        //    setInterval(() => {
        //         time = new Date();
        //         data[index] = time;
        //     }, 1000);
		}
	}
	onMount(()=>{
	    const endTime = +new Date();
		console.log((endTime - beginTime) / 1000,1);
		console.log(data);
		
			setInterval(() => {
				// console.log(123123)
				time = new Date();
				for (let index = 0; index < 6000; index++) {
					data[index] = time;
				}
            }, 1000);
	})
</script>

{#each data as d, i}
<h1 on:click={click(i)}>
	<span>
		<span>
			<span>
				<span>
					Hello {name} {i} {d}!
				</span>
			</span>
		</span>
	</span>
</h1>
{/each}