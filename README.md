import React, { Component } from 'react';
import logo from './logo.svg';

import { Button, FormGroup, FormControl, ControlLabel,TextField,AppBar,RaisedButton } from "react-bootstrap";
import Dropdown from 'react-dropdown'
import 'react-dropdown/style.css'
import './App.css';
import "./login.css";

class App extends Component {
constructor(props) {
    super(props);
    this.state = {username: '',password:'',role:''};

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }


  handleChange(event) {
    this.setState({[event.target.id]: event.target.value});
  }

  validateForm() {
    return this.state.email.length > 0 && this.state.password.length > 0;
  }

  handleSubmit(event) {
    alert('A name was submitted: ' + this.state.username+this.state.password+this.state.role);
     alert(""+this.state.email.length > 0 && this.state.password.length > 0);
     return false;
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" id="username"  value={this.state.username} onChange={this.handleChange} />
        </label>



        <label>
                  Password:
                  <input type="password" id="password" value={this.state.password} onChange={this.handleChange} />
                </label>
                <label> Choose Role:
                <select id="role"
                        value={this.state.role}
                        onChange={this.handleChange}
                      >
                      <option value="Select">Select your ROLE</option>
                       <option value="Doctor">Doctor</option>
                        <option value="Patient">Patient</option>
                        <option value="Guest">Guest</option>
                      </select></label>
        <input type="submit" value="Submit" />
      </form>


    );
  }
}

export default App;
/*
@media all and (min-width: 480px) {
  .Login {
    padding: 60px 0;
  }

  .Login form {
    margin: 0 auto;
    max-width: 320px;
  }
}*/
