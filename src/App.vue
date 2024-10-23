<template>
    <v-app>
        <v-app-bar :elevation="2">
            <template v-slot:append>
                <v-btn color="primary" prepend-icon="mdi-compare" @click="isDark = !isDark; $vuetify.theme.name = isDark ? `dark` : `light`;">
                    {{ isDark ? "Dark" : "Light" }}
                </v-btn>
            </template>

            <v-app-bar-title>QLearn Sucks</v-app-bar-title>
        </v-app-bar>
        <v-main class="d-flex justify-center">
            <div class="content pa-5">
                <!-- <v-alert
                    closable
                    icon="mdi-account-voice"
                    title="Content warning"
                    text="This website contains strong language. If you are a little child who cannot handle big words, you should leave."
                    color="primary"
                    class="mb-5"
                ></v-alert> -->

                <h1>UI Design</h1>
                <p>
                    Let's start off with the UI. It's not the <!-- shittiest --> worst in the world, but it does get the job done.
                </p>
                <p>
                    Firstly, what the <!-- fuck --> <s>hell</s> sigma is this sidebar?
                </p>
                <br>
                <v-card :elevation="12">
                    <v-img src="@/assets/ui-sidebar.png"></v-img>
                </v-card>
                <br>
                <p>
                    Why do I need a <!-- fucking --> scrollbar to see the whole navigation menu? Why do students
                    need a 4K monitor to use your <!-- shitty --> bad navigation? Developers will be going crazy after
                    they find out what a <!-- fucking --> overflow menu is.
                </p>
                <p>
                    The worst part is you made an overflow menu on mobile. You might want to try out this
                    life hack I found, it's called "Copy and Paste." 
                </p>
                <br>
                <h1>Accessibility</h1>
                <p>
                    The only <!-- fucking --> accessibility feature on this website is an immersive reader.
                </p>
                <p>
                    There's also a high contrast mode, but it is arse. Look at how effective this <!-- shit --> is:
                </p>
                <br>
                <v-card :elevation="12">
                    <v-img src="@/assets/high-contrast.png"></v-img>
                    <v-card-text>
                        <v-icon>mdi-information</v-icon>
                        Left: High contrast OFF, Right: High contrast ON
                    </v-card-text>
                </v-card>
                <br>
                <p>
                    They must not give a <!-- shit --> damn about users. They just made the sidebar lighter and called it a <!-- fucking --> day.
                </p>
                <br>
                <h1>Dark Mode</h1>
                <p>Title says it all. Even I managed to do it.</p>
                <br>
                <v-card :elevation="12">
                    <v-card-text>
                        Currently, {{ isDark ? "dark" : "light" }} mode is on.
                    </v-card-text>
                    <v-card-actions>
                        <v-spacer></v-spacer>
                        <v-btn color="primary" @click="isDark = !isDark; $vuetify.theme.name = isDark ? `dark` : `light`;">Toggle dark/light mode</v-btn>
                        <v-spacer></v-spacer>
                    </v-card-actions>
                </v-card>
                <v-card class="mt-5">
                    <v-card-text>
                        <p><em><b>This website is not affiliated to Canvas or QLearn in any way.</b></em></p>
                        <p>
                            This domain expires in {{ s }}.
                        </p>
                        <br>
                        <p>
                            This website was created by <a href="https://infinity-atom.org">infinity-atom</a>.<br>
                            &copy; 2024 infinity-atom
                        </p>
                    </v-card-text>
                </v-card>
            </div>
        </v-main>
    </v-app>
</template>

<style scoped>
    .content {
        max-width: 650px;
        width: 100vw;
    }
</style>

<script setup>
    import { ref } from "vue";

    const isDark = ref(true);
    const s = ref("1 month, 2 days, 3 hours, 4 minutes, and 5 seconds");

    const expiry = new Date("May 10, 2025 00:00:00");
    setInterval(() => {
        // Change s variable every second

        const now = new Date();
        const diff = expiry - now;

        const days = Math.floor(diff / (1000 * 60 * 60 * 24));
        const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((diff % (1000 * 60)) / 1000);

        s.value = `${days} day${days == 1 ? "" : "s"}, ${hours} hour${hours == 1 ? "" : "s"}, ${minutes} minute${minutes == 1 ? "" : "s"}, and ${seconds} second${seconds == 1 ? "" : "s"}`;
    }, 500);
</script>