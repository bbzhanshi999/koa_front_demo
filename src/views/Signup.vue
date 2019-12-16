

<script>
export default {
  /*  render: function(createElement) {
    var self = this;
    return createElement("div", [
      createElement(
        "div",
        {
          class: {
            foo: true,
            bar: false
          },
          domProps: {
            id: "haha"
          }
        },
        [
          createElement("label", "用户名"),
          createElement("input", {
            domProps: {
              value: self.user.username
            },
            on: {
              input: function(event) {
                console.log(event.target.value)
                //self.$emit("input", event.target.value);
                self.user.username = event.target.value
              }
            }
          }),
          createElement('h1',this.user.username)
        ]
      )
    ]);
  }, */
  render() {
    const inputAttrs = {
      type: "email",
      placeholder: "Enter your email"
    };
    return (
      <div>
        <div>
          <label>用户名:</label>
          <input type="text" vModel={this.user.username} />
        </div>
        <h1>{this.user.username}</h1>
        <input {...{ attrs: inputAttrs }} />
      </div>
    );
  },
  data() {
    return {
      user: {
        username: "fdsfdsf",
        password: "",
        age: 0
      }
    };
  },
  methods: {
    submit() {
      axios.post("/signup", this.user).then(res => {
        alert(JSON.stringify(res.data));
      });
    }
  }
};
</script>

<style>
</style>