<script lang="ts">
	import { onMount } from 'svelte'
	import { databases, account } from '$lib/appwrite'
	import { DATABASE_ID, EXPENSES_COLLECTION_ID } from '$lib/appwrite'
	import { Query, Permission, Role } from 'appwrite'
	import { formatDistanceToNow } from 'date-fns'

	let expenses = []
	let loading = true
	let error = null
	let showForm = false
	let formData = {
		amount: '',
		description: '',
		category: 'other'
	}

	let editingExpense = null
	let editFormData = {
		amount: '',
		description: '',
		category: 'other'
	}
</script>
