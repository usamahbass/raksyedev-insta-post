<!-- App.svelte -->

<script>
  import Declaring from "./Declaring.svelte";
  import DefaultValue from "./DefaultValue.svelte";
  import Spread from "./Spread.svelte";

  const myself = {
    name: "RaksyeDev",
    age: "18 years old",
    url: "https://raksyedev.netlify.app/",
  };
</script>

<!-- Delcaring Props  -->
<Declaring answer="Goat" />

<!-- DefaultValue -->
<DefaultValue  />
<DefaultValue answer="Goat" />

<!-- Spread props  -->
<Spread {...myself}/>
