# App.py  
  
  
from flask import Flask, jsonify  
import os  
  
app = Flask(__name__)  
  
@app.route("/ainsten/status")  
def status():  
    return jsonify({  
        "status": "Kernel ativo",  
        "kernel_version": os.environ.get("KERNEL_ID", "unknown"),  
        "note": "Nenhuma medição de tokens no app - módulo P0 desativado aqui"  
    })  
  
if __name__ == "__main__":  
    app.run(host="0.0.0.0", port=int(os.environ.get("PORT", 3000)))  
