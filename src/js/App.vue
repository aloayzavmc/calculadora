<template>
    <div>
        <div>
            <form ref="form" class="space-y-4 text-center">
                <fieldset>
                    <h3 class="mb-3 text-lg font-bold">Estado de consevación</h3>
                    <div class="flex items-center justify-center gap-4">
                        <label for="conservation-option-1">
                            <input type="radio" name="conservation" id="conservation-option-1" value="1" v-model="conservation">
                            Seminuevo
                        </label>
                        <label for="conservation-option-2">
                        <input type="radio" name="conservation" id="conservation-option-2" value="1" v-model="conservation">
                            Nuevo
                        </label>
                        <label for="conservation-option-3">
                            <input type="radio" name="conservation" id="conservation-option-3" value="0" v-model="conservation">
                            Salvamento
                        </label>
                        <label for="conservation-option-4">
                            <input type="radio" name="conservation" id="conservation-option-4" value="0" v-model="conservation">
                            Chatarra
                        </label>
                    </div>
                </fieldset>
                <fieldset>
                    <h3 class="mb-3 text-lg font-bold">Operatividad</h3>
                    <div class="flex items-center justify-center gap-4">
                        <label for="operativity-option-1">
                            <input type="radio" name="operativity" id="operativity-option-1" value="1" v-model="operativity" checked>
                            Operativo
                        </label>
                        <label for="operativity-option-2">
                            <input type="radio" name="operativity" id="operativity-option-2" value="-1" v-model="operativity">
                            Inoperativo
                        </label>
                        <label for="operativity-option-3">
                            <input type="radio" name="operativity" id="operativity-option-3" value="0" v-model="operativity">
                            Siniestrado
                        </label>
                    </div>
                </fieldset>
                <fieldset>
                    <h3 class="mb-3 text-lg font-bold">Ubicación</h3>
                    <div class="flex items-center justify-center gap-4">
                        <label for="location-option-1">
                            <input type="radio" name="location" id="location-option-1" value="1" v-model="location">
                            Lima
                        </label>
                        <label for="location-option-2">
                            <input type="radio" name="location" id="location-option-2" value="-1" v-model="location">
                            Provincia
                        </label>
                    </div>
                </fieldset>
                <fieldset>
                    <h3 class="mb-3 text-lg font-bold">Transferencia y entrega</h3>
                    <div class="flex items-center justify-center gap-4">
                        <label for="transfer-option-1">
                            <input type="radio" name="transfer" id="transfer-option-1" value="1" v-model="transfer">
                            Inmediata post firma
                        </label>
                        <label for="transfer-option-2">
                            <input type="radio" name="transfer" id="transfer-option-2" value="-1" v-model="transfer">
                            Con demora
                        </label>
                    </div>
                </fieldset>
                <fieldset>
                    <h3 class="mb-3 text-lg font-bold">Faltantes - Otros</h3>
                    <div class="flex items-center justify-center gap-4">
                        <label for="missing-option-1">
                            <input type="checkbox" name="missing" id="missing-option-1" value="0" v-model="missing" :disabled="missing.includes('-1')">
                            Sin faltantes
                        </label>
                        <label for="missing-option-2">
                            <input type="checkbox" name="missing" id="missing-option-2" value="-1" v-model="missing" :disabled="missing.includes('0')">
                            Sin llaves
                        </label>
                        <label for="missing-option-3">
                            <input type="checkbox" name="missing" id="missing-option-3" value="-1" v-model="missing" :disabled="missing.includes('0')">
                            Sin tarjeta de propiedad
                        </label>
                    </div>
                </fieldset>
                <fieldset>
                    <h3 class="mb-3 text-lg font-bold">Afectaciones</h3>
                    <div class="flex items-center justify-center gap-4">
                        <label for="encumbrances-option-1">
                            <input type="checkbox" name="encumbrances" id="encumbrances-option-1" value="0" v-model="encumbrances" :disabled="encumbrances.includes('-1')">
                            Sin afectaciones
                        </label>
                        <label for="encumbrances-option-2">
                            <input type="checkbox" name="encumbrances" id="encumbrances-option-2" value="-1" v-model="encumbrances" :disabled="encumbrances.includes('0')">
                            Multas, papeletas, impuestos
                        </label>
                        <label for="encumbrances-option-3">
                            <input type="checkbox" name="encumbrances" id="encumbrances-option-3" value="-1" v-model="encumbrances" :disabled="encumbrances.includes('0')">
                            Gravámenes (que el comprador debe asumir)
                        </label>
                        <label for="encumbrances-option-4">
                            <input type="checkbox" name="encumbrances" id="encumbrances-option-4" value="-1" v-model="encumbrances" :disabled="encumbrances.includes('0')">
                            Orden de captura (Activa al momento de la entrega)
                        </label>
                    </div>
                </fieldset>
            </form>
            <div class="text-center">
                {{ encumbrances }}
                {{ missing }}
                {{ transfer }}
                {{ operativity }}
                {{ conservation }}
                {{ location }}
            </div>
        </div>
    </div>
</template>
<script>
export default{
    data() {
        return {
            encumbrances: [],
            missing: [],
            transfer: null,
            operativity: "1",
            conservation: "1",
            location: null,
        }
    }
}
</script>

