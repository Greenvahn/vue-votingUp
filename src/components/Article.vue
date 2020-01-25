<template>
    <div class="section">
      <article v-for="item in information" class="media" v-bind:key="item.id" v-bind:class="{'blue-border': item.votes >= 20}">
        <figure class="media-left">
          <img class="image is-64x64"
            v-bind:src="item.submissionImage">
        </figure>
        <div class="media-content">
          <div class="content">
            <p>
              <strong>
                <a href="#" class="has-text-info">{{item.title}}</a>
                <span class="tag is-small">#{{item.id}}</span>
              </strong>
              <br>
               {{item.description}}
              <br>
              <small class="is-size-7">
                Submitted by:
                <img class="image is-24x24"
                  v-bind:src="item.avatar">
              </small>
            </p>
          </div>
        </div>
        <div class="media-right" @click="addVote(item.id)">
          <span class="icon is-small">
            <font-awesome-icon icon="chevron-up"></font-awesome-icon>
            <strong class="has-text-info">{{item.votes}}</strong>
          </span>
        </div>
      </article>
    </div>
</template>

<script>
export default {
  name: 'Article',
  props: {
      information:{
        type: Array,
        required: true
      }
  },
  methods: {
    addVote(a){
      const submission = this.information.find(
        item => item.id === a
      );
      submission.votes++;
    }
  }
}
</script>

<style lang="scss">
.media {
  max-width: 600px;
  margin: 0 auto;
  border: 1px solid #e6e7e9;
  padding: 1em 1.5em 0.5em 1.5em;
  border-radius: 0.3em;
}

.image.is-24x24{
  display: inline;
  position: relative;
  top: 5px;
}

.blue-border{
  border-color: #3298dc;
  border-bottom: 5px solid #3298dc;
}

.media-right{
  cursor: pointer;
}
</style>