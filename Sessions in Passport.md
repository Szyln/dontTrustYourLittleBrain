# Sessions in Passport
>- 需安裝 [[cookie-session]]
>- [passport.js doc>configure](https://www.passportjs.org/docs/configure/)

僅將 userID 存進 [[Session]]

```js
// import 之後
// 進行
passport.serializeUser((user, done) => {
	console.log('Serializing user now');
	// mongoDB 存取的 id 要加底線（我不懂）
  done(null, user._id);
});

passport.deserializeUser((_id, done) => {
	console.log('Deserializing user now');
  User.findById({ _id }).then(() => {
		console.log('found user.')
		done(null, user);
  });
});
```
```js

// cookie session 的 middleware 之後
app.use(passport.initialize());
app.use(passport.session());
```
