<script lang="ts">
    export let keyBtn: string | number
    export let gridColSpan: number
    export let isFuncKey: boolean
    export let onClick: (keyBtn: string | number) => void
</script>

<div class={`btn ${isFuncKey ? 'func' : ''}`} style={ `grid-column: span ${gridColSpan} / span ${gridColSpan}`} on:click={()=>onClick(keyBtn)}>
    <span>
        {keyBtn}
    </span>
</div>

<style lang="scss" type="module">
    .btn {
        border-radius: 1rem;
        padding: 0.5rem;
        width: 100%;
        height: 100%;
        font-size: x-large;
        display: flex;
        flex-direction: column;
        justify-content: center;
        transition: all ease-in-out 100ms;

        &:hover {
            filter: drop-shadow(0 0 .25rem #606173aa) blur(1px);		
            transform: scale(0.90);
        }
        
        @media (prefers-color-scheme: light) {
            &:hover {
                filter: drop-shadow(0 0 10rem #242424aa) blur(1px);		
            }
        }	

        &:not(.func){
            @media (prefers-color-scheme: light) {
                & {
                    background-color: rgba($color: #868686, $alpha: 0.8);
                    border: 1px solid rgba($color: #6b6b6b, $alpha: 0.8);		
                }
            }
        
            background-color: rgba($color: #3b3b3b, $alpha: 0.8);
            border: 1px solid rgba($color: #6e6e6e, $alpha: 0.8);
        }

        &.func{
            @media (prefers-color-scheme: light) {
                & {
                    background-color: rgba($color: #ff4949, $alpha: 0.8);
                    border: 1px solid rgba($color:#9d0000, $alpha:0.8);		
                }
            }
        
            background-color: rgba($color: #7d0000, $alpha: 0.8);
            border: 1px solid rgba($color:#b20000, $alpha:0.8);
        }

        
    }
</style>