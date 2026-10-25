(function autoNextWatcher() {
    console.log("Watcher active: Videos will be muted, waiting for NEXT button to turn blue...");

    const checkInterval = setInterval(() => {
        // 1. Locate the video on the page
        const video = document.querySelector('video');
        if (video) {
            // Automatically mute the video
            if (!video.muted) {
                video.muted = true;
                console.log("Video muted.");
            }

            // Resume playback if paused
            if (video.paused && !video.ended) {
                video.play().catch(() => {});
            }
        }

        // 2. Locate the NEXT button
        const btn = document.querySelector('a.btn-primary[data-dismiss="modal"]');

        if (btn) {
            // Check if any disabling flags are present
            const hasDisabledClass = btn.classList.contains('disabled');
            const hasPointerEventsBlocked = btn.style.pointerEvents === 'none';
            const isAriaDisabled = btn.getAttribute('aria-disabled') === 'true';

            // Once the button turns blue and becomes active
            if (!hasDisabledClass && !hasPointerEventsBlocked && !isAriaDisabled) {
                console.log("Button is now active! Clicking NEXT...");
                btn.click();
            }
        }
    }, 2000); // Polls every 2 seconds
})();
