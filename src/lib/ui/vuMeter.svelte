<script lang="ts">
    export let size:number = 1.5;
    export let dataArray:Array<boolean> = [true, true, true, true, true, true, true, true, true, true, true, false, false];

        function getTableContent (dataArrayLocal:Array<boolean>)
        {
            let tableContent = ""

            for (let i = 0; i < 13; i++) {
                let value:number = 6-i;
                let strValue:string;

                if (value > 0) strValue = "+" + value.toString();
                else strValue = value.toString();

                if (strValue == "0") strValue = "Limit";

                let color = "#161719"

                let colorIndex = 12-i;
                if (dataArrayLocal[colorIndex]){
                    color = "#00ff00"
                    if (colorIndex >= 7) color = "#ff0000"
                }

                tableContent += `<tr><td style="background-color: ${color}; width: ${size+2}vw; height: ${size+1}vw; border-radius: ${size-1.1}vw;"></td><td style="font-size: ${size}vw; color: grey;">${strValue}</td></tr>`
            }
            return tableContent;
        }

    

</script>

<style lang="scss">
    .main {
        display: flex;
        align-items: center;
    }
</style>


<div class="main">
    <table>
        {@html getTableContent(dataArray)}
    </table>

</div>