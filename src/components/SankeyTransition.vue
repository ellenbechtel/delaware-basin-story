<template>
  <div id="sankey-transition">
    <div id="sankey-image-container-outer">
      <div id="sankey-image-container-inner">
        <img
          id="sankey-image-5"
          src="@/assets/components/sankeyTransition/images/sankey-res-shapes_Release.png"
          alt=""
        >
        <img
          id="sankey-image-4"
          src="@/assets/components/sankeyTransition/images/sankey-res-shapes_LowFlow.png"
          alt=""
        >
        <img
          id="sankey-image-3"
          src="@/assets/components/sankeyTransition/images/sankey-res-shapes_Withdrawals.png"
          alt=""
        >
        <img
          id="sankey-image-2"
          src="@/assets/components/sankeyTransition/images/sankey-res-shapes_Reservoirs.png"
          alt=""
        >
        <img
          id="sankey-image-1"
          src="@/assets/components/sankeyTransition/images/sankey-res-shapes_Basin.png"
          alt=""
        >
      </div>
    </div>
    <div
      id="sankey-text-container"
      class="text-content-side"
    >
      <div
        id="sankey-text-and-title-1"
        v-observe-visibility="{
          callback: visibilityChanged,
          intersection: {
            rootMargin: '-49% 0% -50% 0%',
            threshold: 0
          }
        }"
        class="scrolly-chunk"
      >
        <div
          id="p-container-1"
          class="p-container text-content-side text-chunk"
        >
          <h3
            id="sankey-title-1"
          >
            Managing River Flows
          </h3>
          <p>Flow in the Basin today is managed through formal cooperation among federal, state, and local entities. This cooperation works to ensure that even at times of greatest need, there’s still plenty of water to flow downriver into the Delaware Bay.</p>
          <p><span class="emph">Reservoirs</span> help us manage that flow. </p>
        </div>
      </div>

      <div
        id="sankey-text-and-title-2"
        v-observe-visibility="{
          callback: visibilityChanged,
          intersection: {
            rootMargin: '-49% 0% -50% 0%',
            threshold: 0
          }
        }"
        class="scrolly-chunk"
      >
        <div
          id="p-container-2"
          class="p-container text-content-side text-chunk"
        >
          <h3
            id="sankey-title-2"
          >
            Reservoirs
          </h3>
          <p>
            <a
              href="https://webapps.usgs.gov/odrm/data/data.html"
              target="_blank"
            >Reservoirs</a> act as storage tanks that hold enormous amounts of water for times when we need it. They are also used for other kinds of water management - flood control, hydroelectric power, and recreation.
          </p>
        </div>
      </div>
      <div
        id="sankey-text-and-title-3"
        v-observe-visibility="{
          callback: visibilityChanged,
          intersection: {
            rootMargin: '-49% 0% -50% 0%',
            threshold: 0
          }
        }"
        class="scrolly-chunk"
      >
        <div
          id="p-container-3"
          class="p-container text-content-side text-chunk"
        >
          <h3
            id="sankey-title-3"
          >
            Using the Reservoirs
          </h3>
          <p>
            Major water users like New York City, Philadelphia, and the entire state of New Jersey are allowed to withdraw water from the river and reservoirs for public supply. The River Master and others use <a
              href="https://waterdata.usgs.gov/usa/nwis/"
              target="_blank"
            >water data collected by the USGS</a> to inform major users on how much water is stored in these reservoirs and when releases are needed to manage flow objectives on the river.
          </p>
          <p>But the water cycle has a big say in how much water is available, too.</p>
        </div>
      </div>
      <div
        id="sankey-text-and-title-4"
        v-observe-visibility="{
          callback: visibilityChanged,
          intersection: {
            rootMargin: '-49% 0% -50% 0%',
            threshold: 0
          }
        }"
        class="scrolly-chunk"
      >
        <div
          id="p-container-4"
          class="p-container text-content-side text-chunk"
        >
          <h3
            id="sankey-title-4"
          >
            Summer Lows
          </h3>
          <p>In the late summer of most years, the streams and rivers of the Basin have lower, slower flows.  The normal low flows are exacerbated during summers with droughts.  But even with low flows, human water demands don’t let up!</p>
          <p>The Supreme Court, as part of the decree, mandated an important flow target at Montague, NJ. The Delaware Basin Compact mandated an additional flow objective at Trenton, NJ.  Those minimum-flow targets are designed to protect fair water distribution, so there’s enough water to provide for the needs of downstream users – human and otherwise.</p>
        </div>
      </div>
      <div
        id="sankey-text-and-title-5"
        v-observe-visibility="{
          callback: visibilityChanged,
          intersection: {
            rootMargin: '-49% 0% -50% 0%',
            threshold: 0
          }
        }"
        class="scrolly-chunk"
      >
        <div
          id="p-container-5"
          class="p-container text-content-side text-chunk"
        >
          <h3
            id="sankey-title-5"
          >
            Reservoir Releases
          </h3>
          <p>But with careful management, reservoirs can provide a buffer against these excessively low flows.  When there’s a chance that the amount of water in the river could drop below the flow targets, the River Master and DRBC will decide to call for release of some of the stored water at just the right rate and time to fill the gap.</p>
          <p>With accurate data and smart management, there’s enough water available for everyone. </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SankeyTransition',
  methods: {
    visibilityChanged(isVisible, entry) {
      const imageElement = document.getElementById('sankey-image-' + entry.target.id[entry.target.id.length - 1]);
      const paragraphContainerTargetId = 'p-container-' + entry.target.id[entry.target.id.length - 1];
      const paragraphContainerTargetElement = document.querySelector('#' + paragraphContainerTargetId);

      if (isVisible === true) {
        imageElement.classList.add('visible');
        paragraphContainerTargetElement.classList.add('visible');
      } else if (isVisible === false) {
        imageElement.classList.remove('visible');
        paragraphContainerTargetElement.classList.remove('visible');
      }
    }
  }
}
</script>

<style scoped lang="scss">
#sankey-transition {
  display: grid;
  grid-template-columns: 1fr 1fr;
  #sankey-image-container-inner {
    position: sticky;
    top: 10%;
    display: grid;
    grid-template-columns: 1fr;
    justify-items: center;
    #sankey-image-1 {
      grid-column: 1;
      grid-row: 1;
      align-self: start;
    }
    #sankey-image-2 {
      grid-column: 1;
      grid-row: 1;
      align-self: start;
    }
    #sankey-image-3 {
      grid-column: 1;
      grid-row: 1;
      align-self: start;
    }
    #sankey-image-4 {
      grid-column: 1;
      grid-row: 1;
      align-self: start;
    }
    #sankey-image-5 {
      grid-column: 1;
      grid-row: 1;
      align-self: start;
    }
    img {
      opacity: 0;
      transition: opacity .5s;
      max-height: 80vh;
    }
    img.visible {
      opacity: 1;
    }
  }

  // controls the text fades
  .p-container {
    opacity: 0;
    transition: opacity .5s;
  }
  .p-container.visible {
    opacity: 1;
  }
}

@media only screen and (max-width: 992px) {
  #sankey-transition {
    display: grid;
    grid-template-columns: 1fr;
    justify-items: center;

    #sankey-text-container {
      z-index: 2;
    }
  }

  #sankey-image-container-outer {
    z-index: 1;
    position: sticky;
    top: 0;
    grid-column: 1;
    grid-row: 1;
    align-self: start;
  }
  #sankey-text-container {
    grid-column: 1;
    grid-row: 1;
    align-self: start;
  }
}
</style>