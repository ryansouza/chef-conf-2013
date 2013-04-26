## Managing Resources and their Providers

##### Miah Johnson (Devops Engineer at HotelTonight)

- recipe that does everything
    - switching based on attributes
    - not flexible, combining responsibilities

- composable recipes
    - split up big recipe in to separate bits
    - still limited to a single "run"
    - still lots of information living in attributes

- library as a resource
    - unique names
    - no crazy attr switches
    - stable public interface (params to a resource)
    - expose actions
    - flexibility
    - use attributes for more global options

- providers
    - "localized" code
    - you can even override chef providers
    - (how can we override default providers?)
