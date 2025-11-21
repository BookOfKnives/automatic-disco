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
  // console.log("start of sortname, users:", usersArray)
    let sortedUserArray = [];
    userArray = userArray.sort(function (a, b){
      // console.log("inside sortname, a b:", a, b)
      if (a.username < b.username){
        // console.log("uysernme:", a.username)
        return -1;
      }
      if (a.username > b.username) {
        return 1;
      }
      return 0;
    })
    console.log("sorted users array:", sortedUserArray);
    return sortedUserArray;
}

</script>

<main>
  <p>Hello and welcome.</p>
<div>
    <table>
        <thead>
    <!-- {#each userArray as person} -->
             <tr>
                <th>
                  User ID #
                   <!-- {person['username']} -->
             </th>
             <th on:click={() => sortName(userArray)}>Username</th>
             <th>Email</th>
             <th>Birthday</th>
            </tr>
<!-- {/each} -->
            </thead>
            <tbody>

          {#each userArray as person}
          
         <tr>
            <th>
                {person['userId']}
            </th>
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
