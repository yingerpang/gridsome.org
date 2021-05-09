<template>
  <Section class="intro" dots="true">
    <div class="container text-center ">
        <h1 class="intro__title">
          <span>海数组件库</span>
        </h1>
    </div>
  </Section>
</template>

<static-query>
query {
  metadata {
    gridsomeVersion
  }
}
</static-query>

<style lang="scss">
.intro {
  width:100%;
  padding: calc(2% + var(--space)) 0;
  display: flex;
  align-items: center;
  &__title {
    font-size: 3rem;
    font-weight: 600;
    margin-left: auto;
    margin-right: auto;

    @media screen and (max-width: 850px) {
      & {
        font-size: 2rem;
      }
    }
  }

  &__lead {
    max-width: 650px;
    margin-left: auto;
    margin-right: auto;
    font-size: 1.3rem;

    @media screen and (max-width: 850px) {
      & {
        font-size: 1rem;
      }
    }
  }

  &__info {
    font-size: .9rem;
  }

  &__keywords {
    position: relative;
    display: block;
  }
}
</style>
