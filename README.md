Frontend Port Forwarding - kubectl port-forward svc/tradein-frontend-service 31000:80 --address 0.0.0.0 &
Backend Port Forwarding - kubectl port-forward svc/tradein-backend-service 8000:8000 --address 0.0.0.0 &
