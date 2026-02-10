<script setup>
import ContentItem from './ContentItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
</script>

<template >
  <div style="display: block;">
    <ContentItem>
      <template #icon>
        <DocumentationIcon />
      </template>
      <template #heading>Risk</template>
      Att besöka den här sidan sker på egen risk. Utvärdera hur mycket risk din portfölj har råd att ta på sig innan du fortsätter. 
    </ContentItem>

    <ContentItem>
      <template #icon>
        <ToolingIcon />
      </template>
      <template #heading>Konst</template>
      Varför håller man på att göra konst? Finns det inte bättre saker att göra av sin tid? Kanske handlar det om att väcka frågor, specifkt hos personer som beger sig till att galleri mentalt inställda på att få frågor väckta hos sig.
    </ContentItem>

    <ContentItem>
      <template #icon>
        <EcosystemIcon />
      </template>
      <template #heading>Boskap</template>
        Kvinnor är som grisar, män är som någon slags insekt. Fast vi kan väl inte tala i så klara kategorier, ta ett queerperspektiv. Allt det här är bara fiktion.
    </ContentItem>

    <ContentItem>
      <template #icon>
        <CommunityIcon />
      </template>
      <template #heading>Maskiner</template>
      Jävla maskiner, kan inte leva utan dem, kan inte ens inte vara en av dem, men de kör alltid ihop. Helvete.
    </ContentItem>
    </div>
</template>
