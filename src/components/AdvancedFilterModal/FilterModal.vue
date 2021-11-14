<template>
	<transition name="modal">
		<div class="fixed z-50 top-0 left-0 w-full h-full bg-black bg-opacity-50 table transition-opacity duration-300 ease-in-out">
			<div class="table-cell align-top pt-24">
				<div class="w-96 h-96 shadow shadow-xl mx-auto pt-5 bg-white rounded-sm transition-all duration-300 ease-in-out">
					<div class="mt-0">
						<p class="text-md font-bold">Advanced Filters</p>
					</div>

					<div class="mt-2">
						<p>(Filters)</p>
					</div>

					<div class="mt-3 flex justify-around">
                        <button class="text-sm" @click="$emit('close')">Cancel</button>
						<button class="border py-2 px-3 rounded-md bg-blue-500 text-sm text-white" @click="$emit('close')">Apply</button>
					</div>
				</div>
			</div>
		</div>
	</transition>
</template>

<script></script>

