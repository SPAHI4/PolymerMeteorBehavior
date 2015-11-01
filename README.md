# PolymerMeteorBehavior

Meteor behavior for Polymer

Example usage:

```
<dom-module id="meteor-posts-example">
    <style>
        :host {
            display: block;
        }

    </style>
    <template>
        Logged as: <span>{{currentUser.username}}</span>
        
        <paper-spinner active="{{!isReady}}"></paper-spinner>
        
        <template is="dom-repeat" items="{{posts}}">
          <div class="post">{{item.content}}</div>
        </template>
    </template>
</dom-module>
<script>
    (function () {
        Polymer({
            is: 'meteor-posts-example',

            behaviors: [
                MeteorBehavior
            ],

            autorun: function(){
                this.posts = Posts.find().fetch();
            },

            subscriptions: [['posts']]
        });
    })();
</script>
```
