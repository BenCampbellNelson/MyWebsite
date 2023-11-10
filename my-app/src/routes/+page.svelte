<!--HTML-->
<div class="login-box">
	<form>
		<div class="user-box">
			<input type="text" name="" required="" />
			<label>Username</label>
		</div>
		<div class="user-box">
			<input type="password" name="" required="" />
			<label>Password</label>
		</div>

		<a href="#">
			Log in
			<span />
		</a>
	</form>
</div>

<!--CSS-->
<style>
	.login-box {
		position: absolute;
		top: 50%;
		left: 50%;
		width: 40vw;
		padding: 40px;
		transform: translate(-50%, -50%);
		background: var(--tertiary-colour);
		box-sizing: border-box;
		box-shadow: 0 15px 25px rgba(0, 0, 0, 0.6);
		border-radius: 10px;
		font-family: var(--main-font-family);
	}

	.login-box .user-box {
		position: relative;
	}

	.login-box .user-box input {
		width: 100%;
		padding: 10px 0;
		font-size: 16px;
		color: #fff;
		margin-bottom: 30px;
		border: none;
		border-bottom: 1px solid #fff;
		outline: none;
		background: transparent;
	}

	.login-box .user-box label {
		position: absolute;
		top: 0;
		left: 0;
		padding: 10px 0;
		font-size: 16px;
		color: #fff;
		pointer-events: none;
		transition: 0.5s;
	}

	.login-box .user-box input:focus ~ label,
	.login-box .user-box input:valid ~ label {
		top: -20px;
		left: 0;
		color: #bdb8b8;
		font-size: 12px;
	}

	.login-box form a {
		position: relative;
		display: inline-block;
		padding: 10px 20px;
		color: #ffffff;
		font-size: 16px;
		text-decoration: none;
		text-transform: uppercase;
		overflow: hidden;
		transition: 0.5s;
		margin-top: 40px;
		letter-spacing: 4px;
		border-radius: 20px;
	}

	.login-box a:hover {
		background: var(--secondary-colour);
		color: #fff;
	}

	@media (max-width: 800px) {
		.login-box {
			width: 70vw;
		}
	}
</style>
