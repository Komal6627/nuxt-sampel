<template>
    <div>
        <Title>Nuxt Proj</Title>
        <nav>
            <ul>
                <li>
                    <NuxtLink to="/">Home</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/about">About</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/contact">Contact Us</NuxtLink>
                </li>
            </ul>
        </nav>
        <slot/>
    </div>
</template>