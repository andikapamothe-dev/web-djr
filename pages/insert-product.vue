<template>
    
</template>

<script>
    export async function createUser(data) {
    const response = await fetch('http://165.22.61.192:9911', {
        method: 'POST',
        headers: {'Content-Type': 'application/json'},
        body: JSON.stringify(data)
      })
    return await response.json();
}
</script>