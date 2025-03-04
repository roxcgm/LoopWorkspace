LoopWorkspace-level patches can be saved in this directory (LoopWorkspace/patches/)
public static let defaultCarbAbsorptionTimes: CarbStore.DefaultAbsorptionTimes = (fast: .hours(1.5), medium: .hours(3), slow: .hours(5))
let automaticDosingIOBLimit = maxBolus! * 3.0
static let bolusPartialApplicationFactor = 0.5
private let allScaleFactorPercentages = Array(stride(from: 50, through: 200, by: 5))
