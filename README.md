# two-pod-comm

step 1 : Download the repository by using 
  git clone https://github.com/yusufsiddiqui26/two-pod-comm.git

step 2 : apply the file in kubernetes cluster
kubectl apply -f ./two-ns-comm 


step 3 : As network policy is applied on ingress traffic on Dev pod over 80 port curl cmd work on Dev pod from Production namespace
   To test perform below action
   i) login on prod nginx container
      kubectl -n production exec nginx -it -- bash
      #Inside Pod #>  curl nginx-dev-svc.development.svc.cluster.local

   ii) But it will not work on prod pod as we have not applied any network policy. to test perform below action
      kubectl -n development exec nginx -it -- bash
      #Inside Pod #>  curl nginx-prod-svc.production.svc.cluster.local    ## It will not work
 
