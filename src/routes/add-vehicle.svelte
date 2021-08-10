<script>
import { goto } from '$app/navigation';

    import { Col, Row } from 'sveltestrap';
import authStore from '../stores/authStore';

    authStore.subscribe(async({isLoggedIn, firebaseControlled
    }) => {
        if (!isLoggedIn && firebaseControlled) {
            await goto("/login");
        }
    })
    
</script>

<Row>
    <Col>
    <h1>Add Vehicle</h1>
    <h3>Please Enter A Fleet Vehicle</h3>
    </Col>
</Row>