<template>
	<div class="min-h-screen flex flex-col items-center justify-center">
		<UserDropdown />
		<div class="w-full max-w-md mb-8">
			<div class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
				<textarea
					class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline mb-4"
					placeholder="What's happening?"
				></textarea>
				<div class="flex items-center justify-between">
					<label class="text-gray-500 flex items-center cursor-pointer">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke-width="1.5"
							stroke="currentColor"
							class="w-6 h-6"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								d="M2.25 15.75l5.159-5.159a2.25 2.25 0 013.182 0l5.159 5.159m-1.5-1.5l1.409-1.409a2.25 2.25 0 013.182 0l2.909 2.909m-18 3.75h16.5a1.5 1.5 0 001.5-1.5V6a1.5 1.5 0 00-1.5-1.5H3.75A1.5 1.5 0 002.25 6v12a1.5 1.5 0 001.5 1.5zm10.5-11.25h.008v.008h-.008V8.25zm.375 0a.375.375 0 11-.75 0 .375.375 0 01.75 0z"
							/>
						</svg>
						<input type="file" class="hidden" @change="handleFileChange" />
					</label>

					<button
						class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
						type="button"
						@click="handleSubmit"
					>
						Post
					</button>
				</div>
			</div>
		</div>
		<div class="w-full max-w-md">
			<!-- Daftar Tweet -->
			<!-- Contoh menggunakan v-for untuk menampilkan daftar tweet -->
			<div
				v-for="(tweet, index) in tweets"
				:key="index"
				class="mb-4 bg-white shadow-md rounded p-4"
			>
				<p>{{ tweet.content }}</p>
				<img
					v-if="tweet.image"
					:src="tweet.image"
					alt="Tweet Image"
					class="mt-2 max-w-full h-auto"
				/>
				<div class="mt-2 text-gray-500">Posted by: {{ tweet.author }}</div>
				<!-- Tombol untuk melihat detail tweet atau menambahkan komentar -->
				<button class="text-blue-500 hover:underline mt-2">View Details</button>
			</div>
		</div>
	</div>
</template>

<script>
import UserDropdown from './UserDropdown.vue';

export default {
	data() {
		return {
			tweets: [
				{ content: 'First tweet!', author: 'user1', image: 'url_to_image' },
				{ content: 'Second tweet!', author: 'user2', image: null },
				// ... tambahkan tweet lainnya
			],
		};
	},
	methods: {
		handleFileChange(event) {
			const file = event.target.files[0];
			// Handle the file as needed, for example, you can upload it to a server or display it in the UI.
		},
		handleSubmit() {
			// Logika untuk mengirimkan tweet
			console.log('Tweet submitted!');
		},
	},
	components: { UserDropdown },
};
</script>
