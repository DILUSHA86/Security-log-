# Security-log-
Wife protection 
async evaluateInteraction(cursorVelocity, dwellTime) {
    return tf.tidy(async () => {
        const inputVector = tf.tensor2d([[cursorVelocity, dwellTime]]);
        const prediction = this.model.predict(inputVector);
        const [probability] = await prediction.data();
        if (probability > 0.75) {
            this.triggerAdaptiveLayout();
        }
        return probability;
    });
}async evaluateInteraction(cursorVelocity, dwellTime) {
    const probability = tf.tidy(() => {
        const input = tf.tensor2d([[cursorVelocity, dwellTime]]);
        const prediction = this.model.predict(input);
        return prediction.dataSync()[0];
    });
    if (probability > 0.75) this.triggerAdaptiveLayout();
}const prediction = this.model.predict(inputVector);
const data = await prediction.data();
const probability = data[0];await model.save('localstorage://my-model');
// To restore:
const model = await tf.loadLayersModel('localstorage://my-model');
