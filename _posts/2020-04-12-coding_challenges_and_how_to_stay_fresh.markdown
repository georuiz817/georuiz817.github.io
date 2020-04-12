---
layout: post
title:      "Coding challenges and how to stay fresh "
date:       2020-04-12 23:12:51 +0000
permalink:  coding_challenges_and_how_to_stay_fresh
---


During this time of quarantine, it's best to keep yourself busy. Applying to jobs is very helpful due to it being time consuming and involving a lot of research on the company/position. However, the long you apply it's easy to forget why you're even applying in the first place. To do development! Which means you need to keep up on your dev skills. 

I personally don't like all those algorithmic JavaScript challenges that contains things like fizzbuzz. Yes it helps and yes I can do it, but would I even consider that real world experience for what I'd like to do?? I don't really expect to be doing things like that as a Front End Developer, at least most of the time due to the fact that I enjoy things like Sass and BootStrap and building and designing web pages. I'd think more of using JavaScript for animation and OO. Which is why instead of doing those student like code solving challenges I've decided to actually make things! Theirs tons of project examples you can find online to do and can even submit them in for review. 

A few examples are: 

https://www.freecodecamp.org/  - After ever section their are about 5 projects that have you do on codepen.io and submit to their devs for review. It involves examples like building a tribute page, a portfolio page etc.

https://medium.com/better-programming/here-are-6-frontend-challenges-to-code-9952190c97cc - Heavy in vanilla HTML and CSS. These challenges really want you to use your inner artist and create fun things like a credit card forum (real life scenario) bar graphs etc. I've actually done the credit card form and it's quiet fun. They use Vue.js but I've been doing it with React/BootStrap. 


```
import React  from 'react';
import {Container, Col, Row} from 'react-bootstrap';


const CreditBox = () => {

  //const [Memos, setMemos] = useState([]);

   return (
            <div className='CreditBox'>
              <div className="form-group">
                <form className="form-bar">
                  <Row>
                    <Col>
                    <label for='cardnumber'>Card Number</label>
                    <input className="form-control" type="text" name="cardnumber"/>
                    </Col>
                  </Row>
                  <Row>
                    <Col>
                    <label for='cardholder'>Card Holder</label>
                      <input className="form-control" type="text" name="cardholder"/>
                    </Col>
                  </Row>
                  <Row>
                    <Col xs={4}>
                      <label for='month'>Expiration Date</label>
                      <select type="select" name="exp" class="form-control exp">
                        <option value="" disabled="disabled" selected="selected">Mon</option>
                        <option value={1}>01</option>
                        <option value={2}>02</option>
                        <option value={3}>03</option>
                        <option value={4}>04</option>
                        <option value={5}>05</option>
                        <option value={6}>06</option>
                        <option value={7}>07</option>
                        <option value={8}>08</option>
                        <option value={9}>09</option>
                        <option value={10}>10</option>
                        <option value={11}>11</option>
                        <option value={12}>12</option>
                      </select>
                    </Col>
                    <Col xs={4}>
                      <label for='year'><br></br></label>
                      <select type="select" name="exp" class="form-control exp">
                        <option value="" disabled="disabled" selected="selected">Year</option>
                        <option value={2020}>2020</option>
                        <option value={2021}>2021</option>
                        <option value={2022}>2022</option>
                        <option value={2023}>2023</option>
                        <option value={2024}>2024</option>
                        <option value={2025}>2025</option>
                        <option value={2026}>2026</option>
                        <option value={2027}>2027</option>
                        <option value={2028}>2028</option>
                        <option value={2029}>2029</option>
                        <option value={2030}>2030</option>
                      </select>
                    </Col>
                    <Col className='cvv-class' lg={4}>
                      <label for='cvv'>CVV</label>
                      <input id='cvv'  className="form-control" type="number" max='9999'  placeholder="CVV" name="cvv"/>
                    </Col>
                  </Row>
                  <Row>
                    <Col> 
                      <input className="btn btn-warning" type="submit" value="Submit" />
                    </Col>
                  </Row>
                </form>
            </div>
          </div>
            )
          }

export default CreditBox
```

Using React BootStrap it's completely responsive and exciting to do. I'm only about half way but it's quiet challenging. Getting to credit card to actually flip over will be a new feature for me. I'm assuming it'll be an event function but we will see how I decide to approach it. It really gets your inner artist going on how to figure out to make it exactly like the example they provide. 

Overall I believe practice makes perfect. Yes you should learn the fizzbuzz stuff and would consider it the main fundamentals. But I just personally like building web pages instead. Figure out what works best for you and run with it. Theirs 100% a job out there that fits your interests. 



