use serde::{Serialize, Deserialize};
use wasm_bindgen::prelude::*;

#[derive(Deserialize)]
pub struct InputStruct {
    input1: u32,
    input2: u32,
}
#[derive(Serialize)]
pub struct OutputStruct {
    output1: u32,
    status: String,
}
#[wasm_bindgen]
pub fn run(obj: JsValue) -> JsValue {
    let InputStruct { input1, input2 } = obj.into_serde().unwrap();
    let output = OutputStruct {
        output1: input1 + input2,
        status: String::from("Good"),
    };
    JsValue::from_serde(&output).unwrap()
}
