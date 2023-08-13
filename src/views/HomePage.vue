<template>
    <div>
        <HomeBanner />
        <HomeProducts title="Take a look at some of our pets" subtitle="Whats new?" :products="pets" @more="petsMore" />
        <HomeInfoBanner title="One more friend" subtitle="Thousands more fun!"
            description="Having a pet means you have more joy, a new friend, a happy person who will always be with you to have fun. We have 200+ different pets that can meet your needs!"
            :image="require('@/assets/img/info-1.png')" />
        <HomeProducts title="Our Products" subtitle="Hard to choose right products for your pets?" :products="products"
            @more="productsMore" />
        <HomePartners />
        <HomeInfoBanner title="Adoption" subtitle="We need help. so do they." description="Adopt a pet and give it a home,
it will be love you back unconditionally." :image="require('@/assets/img/info-2.png')" secondary />
        <HomeProducts title="Useful pet knowledge" subtitle="You already know ?" articles :products="articles" />
    </div>
</template>

<script>
import HomeBanner from '@/components/Home/HomeBanner.vue';
import HomeInfoBanner from '@/components/Home/HomeInfoBanner.vue';
import HomePartners from '@/components/Home/HomePartners.vue';
import HomeProducts from '@/components/Home/HomeProducts.vue';

export default {
    components: { HomeBanner, HomeProducts, HomeInfoBanner, HomePartners },
    data: () => {
        return {
            pets: [
                {
                    image: require('@/assets/img/pets/1.png'),
                    title: 'MO231 - Pomeranian White',
                    price: '6.900.000 VND',
                    props: {
                        'Gene': 'Male',
                        'Age': '02 months'
                    },
                },
                {
                    image: require('@/assets/img/pets/2.png'),
                    title: 'MO502 - Poodle Tiny Yellow',
                    price: '3.900.000 VND',
                    props: {
                        'Gene': 'Female',
                        'Age': '02 months'
                    },
                },
                {
                    image: require('@/assets/img/pets/3.png'),
                    title: 'MO102 - Poodle Tiny Sepia',
                    price: '4.000.000 VND',
                    props: {
                        'Gene': 'Male',
                        'Age': '02 months'
                    },
                },
                {
                    image: require('@/assets/img/pets/4.png'),
                    title: 'MO512 - Alaskan Malamute Grey',
                    price: '8.900.000 VND',
                    props: {
                        'Gene': 'Male',
                        'Age': '02 months'
                    },
                },
                {
                    image: require('@/assets/img/pets/5.png'),
                    title: 'MO231 - Pembroke Corgi Cream',
                    price: '7.900.000 VND',
                    props: {
                        'Gene': 'Male',
                        'Age': '02 months'
                    },
                },
                {
                    image: require('@/assets/img/pets/6.png'),
                    title: 'MO502 - Pembroke Corgi Tricolor',
                    price: '9.000.000 VND',
                    props: {
                        'Gene': 'Male',
                        'Age': '02 months'
                    },
                },
                {
                    image: require('@/assets/img/pets/7.png'),
                    title: 'MO231 - Pomeranian White',
                    price: '6.500.000 VND',
                    props: {
                        'Gene': 'Male',
                        'Age': '02 months'
                    },
                },
                {
                    image: require('@/assets/img/pets/8.png'),
                    title: 'MO512 - Poodle Tiny Dairy Cow',
                    price: '5.000.000 VND',
                    props: {
                        'Gene': 'Male',
                        'Age': '02 months'
                    },
                },
            ],
            products: [
                {
                    image: require('@/assets/img/products/1.png'),
                    title: 'Reflex Plus Adult Cat Food Salmon',
                    price: '140.000 VND',
                    props: {
                        'Product': 'Dog Food',
                        'Size': '385gm'
                    },
                    gift: 'Free Toy & Free Shaker',
                },
                {
                    image: require('@/assets/img/products/2.png'),
                    title: 'Reflex Plus Adult Cat Food Salmon',
                    price: '165.000 VND',
                    props: {
                        'Product': 'Cat Food',
                        'Size': '1.5kg'
                    },
                    gift: 'Free Toy & Free Shaker',
                },
                {
                    image: require('@/assets/img/products/3.png'),
                    title: 'Cat scratching ball toy kitten sisal rope ball',
                    price: '1.100.000 VND',
                    props: {
                        'Product': 'Toy',
                    },
                    gift: 'Free Cat Food',
                },
                {
                    image: require('@/assets/img/products/4.png'),
                    title: 'MO231 - Pomeranian White',
                    price: '410.000 VND',
                    props: {
                        'Product': 'Toy',
                    },
                    gift: 'Free Cat Food',
                },
                {
                    image: require('@/assets/img/products/5.png'),
                    title: 'NaturVet Dogs - Omega-Gold Plus Salmon Oil',
                    price: '350.000 VND',
                    props: {
                        'Product': 'Dog Food',
                        'Size': '385gm'
                    },
                    gift: 'Free Toy & Free Shaker',
                },
                {
                    image: require('@/assets/img/products/6.png'),
                    title: 'Costumes Fashion Pet Clother Cowboy Rider',
                    price: '500.000 VND',
                    props: {
                        'Product': 'Costume',
                        'Size': '1.5kg'
                    },
                    gift: 'Free Toy & Free Shaker',
                },
                {
                    image: require('@/assets/img/products/7.png'),
                    title: 'Costumes Chicken Drumsti ck Headband',
                    price: '400.000 VND',
                    props: {
                        'Product': 'Costume',
                    },
                    gift: 'Free Cat Food',
                },
                {
                    image: require('@/assets/img/products/8.png'),
                    title: 'Plush Pet Toy',
                    price: '250.000 VND',
                    props: {
                        'Product': 'Toy',
                    },
                    gift: 'Free Food & Shaker',
                },
            ],
            articles: [
                {
                    image: require('@/assets/img/articles/1.png'),
                    category: 'Pet knowledge',
                    title: 'What is a Pomeranian? How to Identify Pomeranian Dogs',
                    description: 'The Pomeranian, also known as the Pomeranian (Pom dog), is always in the top of the cutest pets. Not only that, the small, lovely, smart, friendly, and skillful circus dog breed.',
                },
                {
                    image: require('@/assets/img/articles/2.png'),
                    category: 'Pet knowledge',
                    title: 'Dog Diet You Need To Know',
                    description: "Dividing a dog's diet may seem simple at first, but there are some rules you should know so that your dog can easily absorb the nutrients in the diet. For those who are just starting to raise dogs, especially newborn puppies with relatively weak resistance.",
                },
                {
                    image: require('@/assets/img/articles/3.png'),
                    category: 'Pet knowledge',
                    title: 'Why Dogs Bite and Destroy Furniture and How to Prevent It Effectively',
                    description: 'Dog bites are common during development. However, no one wants to see their furniture or important items being bitten by a dog.',
                }
            ]
        }
    },
    methods: {
        petsMore() {
            alert('Go to pets more page')
        },
        productsMore() {
            alert('Go to products more page')
        }
    }
}
</script>