<!--
 @component
 This component holds the buttons and logic for our signup/login/logout
 functionality. We're keeping the button UI and function logic in the same file
 for the sake of simplicity. This component is then imported and used in the
 `$lib/components/ui/Header.svelte` component, which in turn is placed on the
 page in the `/src/routes/+layout.svelte` file.

 In its bare state, all the buttons will always show, and there's no actual
 logging in, signing up, etc. taking place. We've also not pre-coded any way to
 _store_ the passkey ID or smart wallet address, once it is known. Perhaps for
 that, you'll use a database, or localStorage, or something else entirely. It's
 up to _you_ to provide the functionality you want to see here, this component
 is merely a canvas for you to paint on.

 We do provide some toast logic for informing users of errors, but you can
 modify/delete that as you see fit.
-->

<script lang="ts">
    // We're using toasts to display errors to the user. We're not doing much
    // error _handling_, though. So, use whatever techniques you see fit.
    import { toaster } from '$lib/toaster';

    /**
     * Sign up as a new user, creating a smart wallet along the way.
     */
    async function signup() {
        console.log('signing up');
        try {
            // Implement the signup logic here
        } catch (err) {
            console.error(err);
            toaster.error({
                title: 'Error',
                description: 'Something went wrong signing up. Please try again later.',
            });
        }
    }

    /**
     * Log in as an existing user, connecting to a pre-existing smart wallet.
     */
    async function login() {
        console.log('logging in');
        try {
            // Implement the login logic here
        } catch (err) {
            console.error(err);
            toaster.error({
                title: 'Error',
                description: 'Something went wrong logging in. Please try again later.',
            });
        }
    }

    /**
     * Log out from the current user session.
     */
    async function logout() {
        console.log('logging out');
        try {
            // Implement the logout logic here
        } catch (err) {
            console.error(err);
            toaster.error({
                title: 'Error',
                description: 'Something went wrong logging out. Please try again later.',
            });
        }
    }
</script>

<div class="flex space-x-1 md:space-x-2">
    <button class="btn preset-filled-primary-500" onclick={signup}>Signup</button>
    <button class="btn preset-tonal-primary" onclick={login}>Login</button>
    <button class="btn preset-tonal-error" onclick={logout}>Logout</button>
</div>
