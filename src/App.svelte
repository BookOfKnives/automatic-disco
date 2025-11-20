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
    {#each userArray as person}
             <tr>
                <th>
                   {person['username']}
             </th>
            </tr>
{/each}
        <tr>
            <th>
                
            </th>
            <th>
                t head 2
            </th>
            <th>
                t head 3
            </th>

        </tr>
    </thead>
    <tbody>
        <tr>

            
            <td>1</td>
            <td>11</td>
            <td>111</td>
        </tr>
        <tr>
            
            <td>2</td>
            <td>22</td>
        </tr>
        <tr>

            <td>3</td>
        </tr>
    </tbody>
</table>

</div>
</main>

<style>
  
</style>
