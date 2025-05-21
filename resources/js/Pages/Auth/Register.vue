<script setup>
import GuestLayout from '@/Layouts/GuestLayout.vue';
import InputError from '@/Components/InputError.vue';
import InputLabel from '@/Components/InputLabel.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import TextInput from '@/Components/TextInput.vue';
import { Head, Link, useForm } from '@inertiajs/vue3';

const form = useForm({
    name: '',
    email: '',
    password: '',
    password_confirmation: '',
});

const submit = () => {
    form.post(route('register'), {
        onFinish: () => form.reset('password', 'password_confirmation'),
    });
};
</script>

<template>
    <GuestLayout>
        <Head title="Register" />

        <!-- Add your PNG icon here (optional) -->
        <div class="register-icon">
            <img src="/images/logo-black.png" alt="Register Icon" class="centered-image" />
        </div>

        <form @submit.prevent="submit" class="register-form">
            <div class="form-group">
                <InputLabel for="name" value="Name" class="form-label" />

                <TextInput
                    id="name"
                    type="text"
                    class="form-input"
                    v-model="form.name"
                    required
                    autofocus
                    autocomplete="name"
                />

                <InputError class="error-message" :message="form.errors.name" />
            </div>

            <div class="form-group">
                <InputLabel for="email" value="Email" class="form-label" />

                <TextInput
                    id="email"
                    type="email"
                    class="form-input"
                    v-model="form.email"
                    required
                    autocomplete="username"
                />

                <InputError class="error-message" :message="form.errors.email" />
            </div>

            <div class="form-group">
                <InputLabel for="password" value="Password" class="form-label" />

                <TextInput
                    id="password"
                    type="password"
                    class="form-input"
                    v-model="form.password"
                    required
                    autocomplete="new-password"
                />

                <InputError class="error-message" :message="form.errors.password" />
            </div>

            <div class="form-group">
                <InputLabel for="password_confirmation" value="Confirm Password" class="form-label" />

                <TextInput
                    id="password_confirmation"
                    type="password"
                    class="form-input"
                    v-model="form.password_confirmation"
                    required
                    autocomplete="new-password"
                />

                <InputError class="error-message" :message="form.errors.password_confirmation" />
            </div>

            <div class="form-actions">
                <Link
                    :href="route('login')"
                    class="forgot-link"
                >
                    Already registered?
                </Link>

                <PrimaryButton
                    class="submit-button"
                    :class="{ 'disabled': form.processing }"
                    :disabled="form.processing"
                >
                    Register
                </PrimaryButton>
            </div>
        </form>
    </GuestLayout>
</template>

<style scoped>
.register-form {
    max-width: 400px;
    margin: 2rem auto;
    padding: 2rem;
    background-color: #151414;
    border-radius: 12px;
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.4);
    color: #ffffff;
}

.form-group {
    margin-bottom: 1.5rem;
}

.form-label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 500;
    color: #ffffff;
}

.form-input {
    width: 100%;
    padding: 0.5rem;
    background-color: #1f1f1f;
    color: #fff;
    border: 1px solid #444;
    border-radius: 6px;
    outline: none;
}

.form-input:focus {
    border-color: #fff;
    box-shadow: 0 0 0 2px #ffffff55;
}

.error-message {
    margin-top: 0.4rem;
    color: #f87171;
    font-size: 0.8rem;
}

.form-actions {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.forgot-link {
    font-size: 0.85rem;
    color: #bbb;
    text-decoration: underline;
    transition: color 0.2s ease;
}

.forgot-link:hover {
    color: #fff;
}

.submit-button {
    background-color: #ffffff;
    color: #151414;
    padding: 0.5rem 1rem;
    border-radius: 6px;
    font-weight: bold;
    cursor: pointer;
    transition: background 0.2s ease;
}

.submit-button:hover {
    background-color: #e5e5e5;
}

.submit-button.disabled {
    opacity: 0.5;
    pointer-events: none;
}

.register-icon {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 1rem;
}

.centered-image {
    width: 150px;
    height: auto;
    display: block;
}
</style>
