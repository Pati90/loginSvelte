<script>
	let email = "";
	let password = "";
  
	function handleSubmit() {
	  if (email && password) {
		const storedUsers = JSON.parse(localStorage.getItem("users")) || [];
		storedUsers.push({ email, password });
		localStorage.setItem("users", JSON.stringify(storedUsers));
		alert("Inicio de sesión exitoso");
		location.reload();
	  } else {
		alert("Por favor ingresá tus credenciales");
	  }
	}
  </script>
  
  <h2 class="text-center mt-5 d-md-block" style="color: blue;"	>Iniciar Sesión</h2>
  <div class="d-flex justify-content-center align-items-center mt-5">
	<form on:submit|preventDefault={handleSubmit}>
	  <div class="form-group">
		<label for="email" class="form-label">Correo Electrónico</label>
		<input
		  type="email"
		  class="form-control"
		  id="email"
		  bind:value={email}
		  required
		/>
	  </div>
	  <div class="form-group">
		<label for="password" class="form-label">Contraseña</label>
		<input
		  type="password"
		  class="form-control"
		  id="password"
		  bind:value={password}
		  required
		/>
		<button type="submit" class="btn btn-primary d-flex" >Iniciar Sesión</button>
	  </div>
	  
	</form>
  </div>
  