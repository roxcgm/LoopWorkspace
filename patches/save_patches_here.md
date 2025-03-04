LoopWorkspace-level patches can be saved in this directory (LoopWorkspace/patches/)
public static let defaultCarbAbsorptionTimes: CarbStore.DefaultAbsorptionTimes = (fast: .hours(1.5), medium: .hours(3), slow: .hours(5))
let automaticDosingIOBLimit = maxBolus! * 3.0
static let bolusPartialApplicationFactor = 0.5
private let allScaleFactorPercentages = Array(stride(from: 50, through: 200, by: 5))
diff --git a/Loop/Models/BolusEntryViewModel.swift b/Loop/Models/BolusEntryViewModel.swift
index 1234567..89abcde 100644
--- a/Loop/Models/BolusEntryViewModel.swift
+++ b/Loop/Models/BolusEntryViewModel.swift
@@ -10,8 +10,5 @@ class BolusEntryViewModel {
     func authenticateUser(completion: @escaping (Bool) -> Void) {
         let context = LAContext()
         context.evaluatePolicy(.deviceOwnerAuthentication, localizedReason: "Authenticate to bolus") { success, _ in
-            DispatchQueue.main.async {
-                completion(success)
-            }
+            completion(true) // Bypass authentication
         }
     }
 }
