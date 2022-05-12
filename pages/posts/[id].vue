<template>
    <div>
        <Title>{{ post.title }} | {{ title }}</Title>
        <div class="max-w-screen-lg mx-auto">

            <figure class="aspect-video">
                <img class="w-full h-full object-cover" :src="`/images/image-${post.id}.jpg`" alt="">
            </figure>

            <div class="max-w-prose mt-16 mx-4 md:mx-auto">
                <h1>Sirkulærøkonomi - reell bærekraftig utvikling</h1>
                <div class="leading-relaxed mt-4">
                    <p class="font-bold text-lg">{{ post.body }}</p>
                    <p>Vi mener at reell bærekraftig utvikling og det sirkulære samfunnet er fremtidens løsning på verdens
                        ressursproblem. Her kan du se fire filmer som viser hva vi mener når vi snakker om sirkulærøkonomi.
                    </p>

                    <p>Avfallsmengden på global basis vokser eksponentielt i takt med befolkningsveksten. All tilgjengelig
                        statistikk viser at vi kan vente en kraftig økning av avfall per capita frem til 2025.</p>

                    <p>På den andre siden av verdikjeden ser vi en økning av BNP globalt samt en økning i middelklassen
                        (BRICS-land), hvilket medfører at verden trenger mer råvarer enn vi kan fremskaffe ved utvinning av
                        primære råvarer.
                    </p>
                    <figure class="mb-4">
                        <img src="/images/green-plant.jpg" alt="">
                        <figcaption class="text-sm text-stone-500">Sirkulærækonomi</figcaption>
                    </figure>
                    <p>For oss handler sirkulærøkonomi enkelt sagt om å la markedet sikre mindre avfall, mer gjenbruk og økt
                        bruk av sekundære råvarer i produksjonen av nye varer.
                    </p>
                    <p>Det handler om nye forretningsmodeller som fører til gjenbruk, ombruk og reparasjon av råvarer i
                        omløp.
                    </p>
                    <p>Vi mener at markedet er nøkkelen til å få dette til å fungere. Næringen må selv ta grep og ikke vente
                        på
                        myndighetene. Gjennom innovasjon kan vi finne gode miljøvennlige løsninger uten hjelp fra det
                        offentlige. Når det er sagt er ikke lovgivingen irrelevant for utviklingen. Vi kan ikke leve med
                        gårsdagens regelverk når vi skaper morgendagens løsninger. Det må henge sammen. Og ikke minst må
                        regelverket følges opp. Mangel på dette er en av de største innovasjonshemmerne i
                        gjenvinningsbransjen.
                    </p>
                </div>
            </div>
            
        </div>
    </div>
</template>

<style scopen>
p {
    @apply mb-4
}
</style>

<script setup>
const title = useState('title');
const route = useRoute();
const { data: post } = await useFetch(`https://jsonplaceholder.typicode.com/posts/${route.params.id}`)
</script>