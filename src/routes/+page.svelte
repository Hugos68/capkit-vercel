<script lang="ts">
    import { Device, type DeviceInfo } from '@capacitor/device';
    
    let deviceInfo: DeviceInfo | null = null;

    async function updateDeviceInfo() {
        deviceInfo = await Device.getInfo();
    }
</script>

<button on:click={updateDeviceInfo}>Get My Device Info Using Capacitor</button>

{#if deviceInfo}
    <p>Info: {JSON.stringify(deviceInfo)}</p>
{/if}
