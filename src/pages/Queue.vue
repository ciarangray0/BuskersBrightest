<template>
    <h1>Welcome to the queue page</h1>
</template>
<script>
import app from '../api/firebase';
import { getFunctions, httpsCallable } from "firebase/functions";
export default {
    name: "Queue",
    created() {
        // Call secure function and load some data
        const functions = getFunctions(app);
        const manageSiteAccess = httpsCallable(functions, 'manageSiteAccess');
        manageSiteaccess()
            .then((result) => {
                // Read result of the Cloud Function.
                /** @type {any} */
                console.log(result);
            });
    }
}

</script> 

