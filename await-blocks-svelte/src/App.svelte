<script>
  let datas = getData();

  async function getData() {
    const res = await fetch(`https://jsonplaceholder.typicode.com/posts`);
    const data = await res.json();

    if (data) {
      return data;
    } else {
      throw new Error(data);
    }
  }

  function handleClick() {
    datas = getData();
  }
</script>

<div class="container my-12 mx-auto px-4 md:px-12">
  <button class="bg-blue-500 hover:bg-blue-400 text-white font-bold py-2 px-4 border-b-4 border-blue-700 hover:border-blue-500 rounded" on:click={handleClick}> load Data </button>

  <div class="flex flex-wrap -mx-1 lg:-mx-4">
    {#await datas}
      <div>loading...</div>
    {:then data}
      {#each data as item}
        <div class="my-1 px-1 w-full md:w-1/2 lg:my-4 lg:px-4 lg:w-1/3">
          <div class="max-w-sm rounded overflow-hidden shadow-lg">
            <div class="px-6 py-4">
              <div class="font-bold text-xl mb-2">{item.title}</div>
              <p class="text-gray-700 text-base">{item.body}</p>
            </div>
          </div>
        </div>
      {/each}
    {:catch err}
      <p>{err}</p>
    {/await}
  </div>
</div>
