<script>
//2011 2025
//21:43
//lets make some code.
console.log("appsvelte online frontend w009")
import { faker } from '@faker-js/faker';
function createRandomUser() {
  return {
    userId: faker.string.uuid(),
    username: faker.internet.username(),
    email: faker.internet.email(),
    birthdate: faker.date.birthdate(),
  };
}

let userArray = [createRandomUser(), createRandomUser(), createRandomUser(), createRandomUser(), createRandomUser()]

function sortName(){
    userArray = userArray.sort(function (a, b){
      if (a.username < b.username){
        return -1;
      }
      if (a.username > b.username) {
        return 1;
      }
      return 0;
    })
}

function sortEmail(){
      userArray = userArray.sort(function (a, b){
      if (a.email < b.email){
        return -1;
      }
      if (a.email > b.email) {
        return 1;
      }
      return 0;
    })
}

function sortUserId(){
      userArray = userArray.sort(function (a, b){
      if (a.userId < b.userId){
        return -1;
      }
      if (a.userId > b.userId) {
        return 1;
      }
      return 0;
    })
}

function sortBirthdate(){
      userArray = userArray.sort(function (a, b){
      if (a.birthdate < b.birthdate){
        return -1;
      }
      if (a.birthdate > b.birthdate) {
        return 1;
      }
      return 0;
    })
}


</script>

<main>
  <p>Hello and welcome.</p>
<div>
    <table>
        <thead>
             <tr>
                <th on:click={() => sortUserId()}> User ID # </th>
                <th on:click={() => sortName()}>Username</th>
                <th on:click={() => sortEmail()}>Email</th>
                <th on:click={() => sortBirthdate()}>Birthday</th>
            </tr>
          </thead>
        <tbody>
          {#each userArray as person}
          <tr>
          <th>{person['userId']}</th>
          <th>{person['username']}</th>
          <th>{person['email']}</th>
          <th>{person['birthdate']}</th>
          </tr>  
          {/each}
       </tbody>
    </table>

</div>
</main>

<style>

table, thead, tr, tbody, th {
  border-style: solid;
} 
tr:hover {
  background-color: #44aa44;
}

</style>
