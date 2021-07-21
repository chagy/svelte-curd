<script>
  let products = [
    {
      id: 1,
      name: "HP Notebook",
      description: "Hp Laptop",
      category: "laptop",
    },
    {
      id: 2,
      name: "Mouse Razer",
      description: "Gaming mouse",
      category: "peripherials",
    },
  ];

  export let product = {
    id: "",
    name: "",
    description: "",
    category: "",
    imageURL: "",
  };

  const onSubmitHandler = (e) => {
    e.preventDefault();
    console.log(e);
  };
</script>

<main>
  <div class="container">
    <div class="row">
      <div class="col-md-6">
        {#each products as product}
          <div class="card mt-2">
            <div class="row">
              <div class="col-md-4">
                <img src="" alt="" />
              </div>
              <div class="col-md-8">
                <h5>
                  <strong>{product.name}</strong>
                  <span><small>{product.category}</small></span>
                </h5>
                <p class="card-text">{product.description}</p>
                <button class="btn btn-danger">Delete</button>
                <button class="btn btn-secondary">Edit</button>
              </div>
            </div>
          </div>
        {/each}
      </div>
      <div class="col-md-6">
        <div class="card">
          <div class="card-body">
            <form on:submit={onSubmitHandler}>
              <div class="form-group">
                <input
                  bind:value={product.name}
                  class="form-control"
                  type="text"
                  placeholder="Product Name"
                  id="product-name"
                />
              </div>
              <div class="form-group">
                <textarea
                  bind:value={product.description}
                  class="form-control"
                  id="product-description"
                  rows="3"
                  placeholder="Product Description"
                />
              </div>
              <div class="form-group">
                <input
                  bind:value={product.imageUrl}
                  class="form-control"
                  type="url"
                  id="product-image-url"
                  placeholder="URL"
                />
              </div>
              <div class="form-group">
                <select
                  id="category"
                  bind:value={product.category}
                  class="form-control"
                >
                  <option value="laptops">Laptops</option>
                  <option value="peripherials">Peripherials</option>
                  <option value="servers">Servers</option>
                </select>
              </div>
              <div class="form-group">
                <button class="btn btn-primary">Save</button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</main>

<style>
</style>
