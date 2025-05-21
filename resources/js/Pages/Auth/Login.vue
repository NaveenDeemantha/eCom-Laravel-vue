<template>
    <GuestLayout>
        <Head title="Log in" />

        <!-- Add your PNG icon here -->
        <div class="login-icon">
            <img src="/images/logo-black.png" alt="Login Icon" class="centered-image" />
        </div>

        <div v-if="status" class="status-message">
            {{ status }}
        </div>

        <form @submit.prevent="submit" class="login-form">
            <div class="form-group">
                <InputLabel for="email" value="Email" class="form-label" />

                <TextInput
                    id="email"
                    type="email"
                    class="form-input"
                    v-model="form.email"
                    required
                    autofocus
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
                    autocomplete="current-password"
                />

                <InputError class="error-message" :message="form.errors.password" />
            </div>

            <div class="checkbox-group">
                <label class="checkbox-label">
                    <Checkbox name="remember" v-model:checked="form.remember" />
                    <span class="checkbox-text">Remember me</span>
                </label>
            </div>

            <div class="form-actions">
                <Link
                    v-if="canResetPassword"
                    :href="route('password.request')"
                    class="forgot-link"
                >
                    Forgot your password?
                </Link>

                <PrimaryButton
                    class="submit-button"
                    :class="{ 'disabled': form.processing }"
                    :disabled="form.processing"
                >
                    Log in
                </PrimaryButton>
            </div>
        </form>
    </GuestLayout>
</template>

<style scoped>
.status-message {
    margin-bottom: 1rem;
    font-size: 0.9rem;
    font-weight: 500;
    color: #4ade80; /* green */
    text-align: center;
}

.login-form {
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

.checkbox-group {
    margin-bottom: 1.5rem;
}

.checkbox-label {
    display: flex;
    align-items: center;
    font-size: 0.9rem;
    color: #ccc;
}

.checkbox-text {
    margin-left: 0.5rem;
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

.login-icon {
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


<script setup>
import Checkbox from '@/Components/Checkbox.vue';
import GuestLayout from '@/Layouts/GuestLayout.vue';
import InputError from '@/Components/InputError.vue';
import InputLabel from '@/Components/InputLabel.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import TextInput from '@/Components/TextInput.vue';
import { Head, Link, useForm } from '@inertiajs/vue3';

defineProps({
    canResetPassword: {
        type: Boolean,
    },
    status: {
        type: String,
    },
});

const form = useForm({
    email: '',
    password: '',
    remember: false,
});

const submit = () => {
    form.post(route('login'), {
        onFinish: () => form.reset('password'),
    });
};
</script>