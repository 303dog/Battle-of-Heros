1. Render array of just the good guys 
2. User should be able to select a good hero, which will be stored in HeroContainer state as "goodGuy"
3. After good guy selection, user should then see a list of just the bad guys. 
4. user should be able to select a bad hero, which will be stored in state as badGuy
5. once both a goodGuy and badGuy have been selected, user sees goodGuy vs badGuy and a fight button
6. after fight is clicked, math is done to declare a winner.
7. selected winner mdimg renders with CHAMP banner and name and a scoreboard button
8. scoreboard directs to champions statistics page

import React from "react";


function EvilHeros(props) {
    return (
      <div className="box">
        <h1>Villians</h1>
        <p>Choose the Opponent!</p>
        {props.evilGuys.map((evilGuy) => {
          return (
            <>
            <div className="evil">
              <p>{evilGuy.name}</p>
              <img src={evilGuy.smImg} alt="evilguy"/>
              <button onClick={() => props.selectEvilGuy(evilGuy)}>select</button>
            </div>
            </>
          );
        })}
      </div>
    );
  }
export default EvilHeros;


import React from "react";


function GoodHeros(props) {
  return (
    <div className="box">
      <h1>Heros</h1>
      <p>Choose your Hero!</p>
      {props.goodGuys.map((goodGuy) => {
        return (
          <>
          <div className="hero">
            <p>{goodGuy.name}</p>
            <img src={goodGuy.smImg} alt="googuy"/>
            <button onClick={() => props.selectGoodGuy(goodGuy)}>select</button>
          </div>
          </>
        );
      })}
    </div>
  );
}

export default GoodHeros;

