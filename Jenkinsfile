@Library('ecommerce-shared-lib') _

microservicePipeline(
    image: "gracekluender/order-service",
    buildCommand: """
        npm install
        npm run lint
    """,
    testCommand: "npm test --passWithNoTests"
)