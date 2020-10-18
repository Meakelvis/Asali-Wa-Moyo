<template>
  <div>
    <EventCard
      title="Honey Tasting"
      image_url="/img/cosmetics.jpg"
      description="Every year we hold a honey tasting event at which we show case all our products and allow the visitors to taste and experiment with them. At this event we also unveil our new products and services. Check our gallery of previous events and get a glimpse of the fun that we had. Due to the COVID19 Pandemic we have postpoined the 2020 Honey tasting event till further notice. P.S. we were the first company to ever hold a honey tasting event in Uganda. Follow us here or any of our social media platforms for news on our next Honey Tasting and other events"
    ></EventCard>
  </div>
</template>

<script>
import EventCard from "@/components/EventCard";

export default {
  components: {
    EventCard,
  },
  //   data:()=> {
  //     events: [
  //       {
  //         id: 1,
  //         title: "Honey Tasting",
  //         description:
  //           "Every year we hold a honey tasting event at which we show case all our products and allow the visitors to taste and experiment with them. At this event we also unveil our new products and services. Check our gallery of previous events and get a glimpse of the fun that we had. Due to the COVID19 Pandemic we have postpoined the 2020 Honey tasting event till further notice. P.S. we were the first company to ever hold a honey tasting event in Uganda. Follow us here or any of our social media platforms for news on our next Honey Tasting and other events",
  //         image_url: "/img/cosmetics.jpg",
  //       },
  //       {
  //         id: 2,
  //         title: "Mandela Week",
  //         description:
  //           "In honour and memory of the great African Leader Nelson Mandela, every year we have a drive where we gift part of our revenue to support a vulnerable group or to support a charitable cause inn Uganda. This is also partly in gratitude to the Mandela Young African Leadership Fellowship Program of the USA government from which we have benefitted as a company.",
  //         image_url: "/img/mullet.jpg",
  //       },
  //     ],
  //   },
};
</script>