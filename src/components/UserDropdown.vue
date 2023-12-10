<template>
	<div class="fixed bottom-0 left-0 mb-4 ml-4">
		<div class="relative inline-block text-left">
			<div>
				<button
					@click="toggleDropdown"
					type="button"
					class="inline-flex justify-center items-center p-2 rounded-full text-gray-600 outline outline-gray-600 outline-offset-2 outline-1 focus:outline-none focus:border-blue-300 focus:ring focus:ring-blue-200 focus:ring-opacity-50"
				>
					<!-- Icon User menggunakan Heroicons -->
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
							d="M15.75 6a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0zM4.501 20.118a7.5 7.5 0 0114.998 0A17.933 17.933 0 0112 21.75c-2.676 0-5.216-.584-7.499-1.632z"
						/>
					</svg>
					Administrator
				</button>
			</div>

			<!-- Dropdown -->
			<div
				v-if="isOpen"
				class="absolute left-0 mb-3 bottom-full w-48 rounded-md shadow-lg bg-white ring-1 ring-black ring-opacity-5"
			>
				<!-- Dropdown content (pilihan logout, dsb.) -->
				<div class="py-1">
					<!-- Contoh pilihan, gantilah sesuai kebutuhan -->
					<button
						@click="logout"
						class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100 w-full"
					>
						Logout
					</button>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			isOpen: false,
		};
	},
	methods: {
		toggleDropdown() {
			this.isOpen = !this.isOpen;
		},
		logout() {
			// Logika untuk melakukan logout, bisa diimplementasikan sesuai kebutuhan
			console.log('Logout');
		},
	},
};
</script>

<style scoped>
/* Sesuaikan dengan kebutuhan gaya Anda */
</style>
