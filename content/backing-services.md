## IV. Backing Services

### Treat backing services as attached resources

Build jobs may depend on backing services such as a database, message queue, or caching service. 
Jobs should be sufficiently abstracted from these backing services so that the physical location of the 
service (local or remote) is abstracted from the job. 
This enables backing services to be swapped out and reconfigured without requiring modification, re-test and 
re-deployment of the job. 

Things get really interesting when your CI system is building and testing a service-oriented application. 
Then, for acceptance testing, services will have dependencies on other upstream services. 
If your services have hard-coded assumptions about the location of upstream services, it makes it very hard 
to verify code along different development streams and branches.

---

<ul class="fa-ul">
    <li>
        <i class="fa-li fa fa-2x fa-check-square"></i>
        <span>A job should work equally well with local or remote backing services.</span>
    </li>
    <li>
        <i class="fa-li fa fa-2x fa-check-square"></i>
        <span>The location of backing services should be provided to the job as configuration.</span>
    </li>
    <li>
        <i class="fa-li fa fa-2x fa-check-square"></i>
        <span>Any secrets needed to connect to a backing service should be provided to the job as configuration.</span>
    </li>
</ul>
