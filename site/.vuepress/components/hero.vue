<template>
  <section
    :class="{
			'hero': true,
			'hero-image': image
		}"
    :style="image && {
			'background-image': `url('${image}')`
		}"
  >
    <div class="hero-body">
      <div :class="['container', containerClass]">
        <div class="hero-content">
          <h3 class="hero-title">{{ title }}</h3>
          <!-- /.hero-title -->
          <div
            v-if="['Home'].includes($page.title)"
            class="hero-subhead"
          >Airship makes operating open infrastructure
            <br>simple, repeatable, and resilient.
          </div>
          <div v-if="withEntry" class="hero-entry">
            <slot name="entry"/>
          </div>
          <!-- /.hero-entry -->
          <div v-if="withButton" class="hero-actions">
            <slot name="buttons"/>
          </div>
          <!-- /.hero-actions -->
        </div>
        <!-- /.hero-content -->
      </div>
      <!-- /.container -->
    </div>
    <!-- /.hero-body -->
  </section>
  <!-- /.hero -->
</template>

<script>
export default {
  /**
   * The name of the component.
   *
   * @type {Strng}
   */
  name: "Hero",

  /**
   * The supported properties of the component.
   *
   * @type {Object}
   */
  props: {
    title: {
      type: String,
      default: () => {}
    },
    image: {
      type: String,
      default: () => {}
    },
    containerClass: {
      type: String,
      default: () => {}
    },
    withEntry: {
      type: Boolean,
      default: false
    },
    withButton: {
      type: Boolean,
      default: false
    }
  }
};
</script>
