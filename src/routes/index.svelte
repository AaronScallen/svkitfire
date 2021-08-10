<script lang="ts">
    import { Row, Col, Button } from "sveltestrap";
    import firebase from "firebase/app";
    import authStore from "../stores/authStore";
    import Navigator from '../components/navbar.svelte'
    async function logout() {
      await firebase.auth().signOut();
    }
    console.log(authStore)
  </script>
  <Navigator />
  <Row>
    <Col>
      <h1>Welcome to NIOC</h1>
      <p>NISD Police Information and Operation Center</p>
    </Col>
  </Row>
  
  {#if $authStore.isLoggedIn}
    <Row>
      <Col>
        <Button on:click={logout} color="danger">Logout</Button>
      </Col>
    </Row>
  {/if}