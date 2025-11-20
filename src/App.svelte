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

// console.log("user?")
console.log(userArray)

</script>

<main>
  <p>Hello and welcome.</p>
</main>

<style>
  
</style>
