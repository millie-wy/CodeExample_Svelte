<script>
    let isHovering;

    const pointTarget = () => {
        isHovering = true;
    };

    const leaveTarget = () => {
        isHovering = false;
    }
</script>

<div on:mouseenter="{pointTarget}" on:mouseleave="{leaveTarget}">
    <slot {isHovering}></slot>
</div>