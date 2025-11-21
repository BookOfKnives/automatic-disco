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

</script>

<main>
  <p>Hello and welcome.</p>
<div>
    <table>
        <thead>
    <!-- {#each userArray as person} -->
             <tr>
                <th>
                  userid
                   <!-- {person['username']} -->
             </th>
             <th>username</th>
             <th>email</th>
             <th>birthday</th>
            </tr>
<!-- {/each} -->
            </thead>
            <tbody>

          {#each userArray as person}
            <th>
                {person['userId']}
            </th>
            <th>{person['username']}</th>
            <th>{person['email']}</th>
            <th>{person['birthdate']}</th>
            {/each}
         <tr>

            </tbody>
</table>

</div>
</main>

<style>

table, thead, tr, tbody, th {
  border-style: solid;
} 
</style>
