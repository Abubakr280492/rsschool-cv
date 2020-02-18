
# Abubakr Abdullaev

[Linked In](https://www.linkedin.com/in/abubakr-abdi-abdullaev-358557150/)
#### +1 5132755276 (American Number)
#### +998 90 110 76 99 (Uzbekistan Number)

## I would like to be one of the best full-stack developer in the world! 

## Skills
+ HTML,CSS,SCSS
+ JavaScript
+ React
+ C++,Java


  ## Code examples

```React
import React from 'react';
import './App.css';
import {Switch, Route, Redirect} from 'react-router-dom';
import {connect} from 'react-redux';

class App extends React.Component {
  unsubscribeFromAuth = null;
  componentDidMount (){ 
    const {setCurrentUser}= this.props;
    this.unsubscribeFromAuth = auth.onAuthStateChanged(async userAuth =>{
      if(userAuth) {
        const userRef = await createUserProfileDocument(userAuth);
        if(userRef) {
         userRef.onSnapshot(snapShot => {
          setCurrentUser({
                id: snapShot.id,
                ...snapShot.data()
              });
          });
        } else {
          alert('There cridential error, please fix it')
        }
      }
      setCurrentUser(userAuth);
    });  
  }
  componentWillUnmount(){
    this.unsubscribeFromAuth();
  }
  //gonna send to the dom 
  render() { 
    return (
      <div >
          <Header/>
        <Switch>
          <Route exact path='/' component={Homepage}/>
          <Route  path='/shop' component={ShopPage}/>  
          <Route exact path='/checkout' component={CheckoutPage}/>  
          <Route exact path='/signin' render={() => 
            this.props.currentUser? (
              <Redirect to='/'/>
            ):(
              <SignInAndSignUpPage />
            )} 
          />
        </Switch>
      </div>
    );
  }
}
//method to combine with redux state
const mapStateToProps = state => ({
  currentUser: selectCurrentUser(state)
});
 
//dispatches actions
const mapDispatchToProps = dispatch => ({
setCurrentUser: user => dispatch(setCurrentUser(user))
});
export default connect(mapStateToProps, mapDispatchToProps )(App);
```


