<script>
	let password = '';
	let length = 12;
	let useLetters = true;
	let useNumbers = true;
	let useSymbols = false;

	const generatePassword = () => {
		const letters = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ';
		const numbers = '0123456789';
		const symbols = "!@#$%^&*()_+-=[]{}|;:',.<>/?";

		let validChars = '';
		if (useLetters) validChars += letters;
		if (useNumbers) validChars += numbers;
		if (useSymbols) validChars += symbols;

		let generatedPassword = '';
		const randomValues = new Uint32Array(length);
		window.crypto.getRandomValues(randomValues);

		for (let i = 0; i < length; i++) {
			generatedPassword += validChars.charAt(randomValues[i] % validChars.length);
		}
		password = generatedPassword;
	};

	$: generatePassword(), length, useLetters, useNumbers, useSymbols;
</script>

<div class="p-4">
	<div class="mb-4">
		<label for="length" class="block text-sm font-medium text-gray-700">Length</label>
		<input
			type="number"
			bind:value={length}
			class="mt-1 block w-full p-2 border border-gray-300 shadow-sm sm:text-sm"
		/>
	</div>
	<div class="mb-4">
		<label class="flex items-center">
			<input type="checkbox" bind:checked={useLetters} class="mr-2" />
			Include Letters
		</label>
		<label class="flex items-center">
			<input type="checkbox" bind:checked={useNumbers} class="mr-2" />
			Include Numbers
		</label>
		<label class="flex items-center">
			<input type="checkbox" bind:checked={useSymbols} class="mr-2" />
			Include Symbols
		</label>
	</div>
	<button
		on:click={generatePassword}
		class="px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600">Generate</button
	>
	<div class="mt-4">
		<label for="output" class="block text-sm font-medium text-gray-700">Generated Password</label>
		<input
			id="output"
			type="text"
			readonly
			bind:value={password}
			class="mt-1 block w-full p-2 border border-gray-300 shadow-sm sm:text-sm"
		/>
	</div>
</div>
