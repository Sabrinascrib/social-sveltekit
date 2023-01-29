<script>
	let  avatar, fileinput;
	
	const onFileSelected =(e)=>{
  let image = e.target.files[0];
            let reader = new FileReader();
            reader.readAsDataURL(image);
            reader.onload = e => {
                 avatar = e.target.result
            };
}
</script>

<div class="app">
	<h1>Upload Image</h1>
  
        {#if avatar}
        <img class="avatar" src="{avatar}" alt="d" />
        {:else}
        <div class="bg-gray-100 w-96"> <img class="avatar upload" src="https://static.thenounproject.com/png/625182-200.png" alt="" on:click={()=>{fileinput.click();}} />
 </div>
       {/if}
				
        <div class="chan" on:click={()=>{fileinput.click();}}>Choose Image</div>
        <input style="display:none" type="file" accept=".jpg, .jpeg, .png" on:change={(e)=>onFileSelected(e)} bind:this={fileinput} >

</div>
