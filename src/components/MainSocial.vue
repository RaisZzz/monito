<template>
    <div class="social">
        <a v-for="(link, index) in links" :key="index" :href="link.link" target="_blank" class="social__link">
            <component class="social__link-icon" :is="link.icon" />
        </a>
    </div>
</template>

<script>
import SocialFacebook from '@/components/Icon/Social/SocialFacebook.vue';
import SocialTwitter from '@/components/Icon/Social/SocialTwitter.vue';
import SocialInstagram from '@/components/Icon/Social/SocialInstagram.vue';
import SocialYouTube from '@/components/Icon/Social/SocialYouTube.vue';

export default {
    components: { SocialFacebook, SocialTwitter, SocialInstagram, SocialYouTube },
    data: () => {
        return {
            links: [
                {
                    icon: SocialFacebook,
                    link: '#',
                },
                {
                    icon: SocialTwitter,
                    link: '#',
                },
                {
                    icon: SocialInstagram,
                    link: '#',
                },
                {
                    icon: SocialYouTube,
                    link: '#',
                }
            ]
        }
    }
}
</script>

<style scoped>
.social {
    display: flex;
    align-items: center;
    gap: 40px;
}

.social__link-icon {
    height: 24px;
    width: auto;
    fill: var(--primary-color);
    transition: var(--transition);
}

.social__link-icon:hover {
    fill: #fff;
}
</style>