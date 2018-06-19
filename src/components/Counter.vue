<template>
  <Page class="page">
    <ActionBar class="action-bar" title="Counter">
      <NavigationButton text="Go Barck" android.systemIcon="ic_menu_back" @tap="$router.push('/home')"/>
    </ActionBar>

    <StackLayout>
      <FlexboxLayout flexDirection="row" justifyContent="center">
        <Button @tap="$store.dispatch('decrement')" text="-" class="btn btn-outline"/>
        <Label :text="message" alignSelf="baseline" class="h2"/>
        <Button @tap="$store.dispatch('increment')" text="+" class="btn btn-outline"/>
      </FlexboxLayout>
      <Image v-if="surprise" src="~/images/NativeScript-Vue.png"/>
    </StackLayout>

  </Page>
</template>

<script lang='ts'>
  import { mapActions } from 'vuex';

  export default {
    computed: {
      message (): string {
        return this.$store.state.counter.count.toString();
      },
      surprise (): boolean {
        return (this.$store.state.counter.count >= 5);
      },
    },
    methods: {
      getString(): string {
        return 'tate';
      }
    },
  };
</script>
