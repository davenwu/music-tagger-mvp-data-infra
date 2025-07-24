# MusicTagger
This contains files for deploying the data infrastructure needed for MusicTagger.

MusicTagger is an application that allows you to add your own tags to songs from your Spotify library. You can then export playlists to Spotify based on any selection of tags.

### Prerequisites
- Kubernetes

### Deploying
> [!WARNING]
> Make sure to set the environment variables to your desired values.

To deploy, run `kubectl apply -f postgres_deployment.yaml`.

In order to access the pgAdmin page, you need to find the `containerPort` of the K8s service that was exposed as well as the IP address of your Kubernetes node (e.g. run `minikube ip` if you're using Minikube).

### Images Used
- `postgres` as the backing SQL database for MusicTagger
- `dpage/pgadmin4` as a GUI to interact with the database for development purposes

### Todo
- Set up separate files for deployment and production (one reason being pgAdmin is not needed in a production environment)

