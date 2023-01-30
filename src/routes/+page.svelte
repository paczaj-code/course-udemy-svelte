<script lang="ts">
	// @ts-nocheck
	import MeetupGrid from '../components/Meetup/MeetupGrid.svelte';
	import TextInput from '../components/UI/TextInput/TextInput.svelte';
	import Button from '../components/UI/Button/Button.svelte';
	let title: string;
	let subtitle: string;
	let imageUrl: string;
	let description: string;
	let address: string;
	let email: string;

	let meetups = [
		{
			id: 'm1',
			title: 'Coding Bootcamp',
			subtitle: 'Learn to code in 2 hours',
			description: 'In this meetup, we will have some experts that teach you how to code!',
			imageUrl:
				'https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Caffe_Nero_coffee_bar%2C_High_St%2C_Sutton%2C_Surrey%2C_Greater_London.JPG/800px-Caffe_Nero_coffee_bar%2C_High_St%2C_Sutton%2C_Surrey%2C_Greater_London.JPG',
			address: '27th Nerd Road, 32523 New York',
			contactEmail: 'code@test.com'
		},
		{
			id: 'm2',
			title: 'Swim Together',
			subtitle: "Let's go for some swimming",
			description: 'We will simply swim some rounds!',
			imageUrl:
				'https://upload.wikimedia.org/wikipedia/commons/thumb/6/69/Olympic_swimming_pool_%28Tbilisi%29.jpg/800px-Olympic_swimming_pool_%28Tbilisi%29.jpg',
			address: '27th Nerd Road, 32523 New York',
			contactEmail: 'swim@test.com'
		}
	];

	function addMeetup() {
		const newMeetup = {
			id: Math.random.toString(),
			title,
			subtitle,
			imageUrl,
			description,
			address,
			email
		};
		//@ts-ignore
		return (meetups = [newMeetup, ...meetups]);
	}
</script>

<!-- @ts-nocheck  -->
<form on:submit|preventDefault={addMeetup}>
	<TextInput
		controlType="text"
		label="Title"
		id="title"
		value={title}
		on:input={(event) => (title = event.target.value)}
	/>
	<TextInput
		controlType="text"
		label="Subtitle"
		id="subtitle"
		value={subtitle}
		on:input={(event) => (subtitle = event.target.value)}
	/>

	<TextInput
		controlType="text"
		label="imageUrl"
		id="imageUrl"
		value={imageUrl}
		on:input={(event) => (imageUrl = event.target.value)}
	/>
	<TextInput
		controlType="text"
		label="Address"
		id="address"
		value={address}
		on:input={(event) => (address = event.target.value)}
	/>
	<TextInput
		controlType="text"
		label="email"
		id="email"
		value={email}
		on:input={(event) => (email = event.target.value)}
	/>
	<TextInput
		controlType="textarea"
		id="description"
		value={description}
		label="Description"
		on:input={(event) => (description = event.target.value)}
	/>
	<Button caption="Add" type="submit" />
	<!-- <button type="submit">Add meetup</button> -->
</form>

<MeetupGrid {meetups} />

<style>
	form {
		width: 30rem;
		max-width: 90%;
		margin: 0 auto;
	}
</style>
