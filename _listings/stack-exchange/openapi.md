swagger: "2.0"
x-collection-name: Stack Exchange
x-complete: 1
info:
  title: Stack Exchange
  description: stack-exchange-is-a-network-of-130-qa-communities-including-stack-overflow-
  version: "2.0"
host: api.stackexchange.com
basePath: /2.2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /filters/create:
    get:
      summary: Create Filter
      description: "Creates a new filter given a list of includes, excludes, a base
        filter, and whether or not this filter should be \"unsafe\".\n \nFilter \"safety\"
        is defined as follows. Any string returned as a result of an API call with
        a safe filter will be inline-able into HTML without script-injection concerns.
        That is to say, no additional sanitizing (encoding, HTML tag stripping, etc.)
        will be necessary on returned strings. Applications that wish to handle sanitizing
        themselves should create an unsafe filter. All filters are safe by default,
        under the assumption that double-encoding bugs are more desirable than script
        injections.\n \nIf no base filter is specified, the default filter is assumed.
        When building a filter from scratch, the none built-in filter is useful.\n
        \nWhen the size of the parameters being sent to this method grows to large,
        problems can occur. This method will accept POST requests to mitigate this.\n
        \nIt is not expected that many applications will call this method at runtime,
        filters should be pre-calculated and \"baked in\" in the common cases. Furthermore,
        there are a number of built-in filters which cover common use cases.\n \nThis
        method returns a single filter."
      operationId: creates-a-new-filter-given-a-list-of-includes-excludes-a-base-filter-and-whether-or-not-this-filter-
      x-api-path-slug: filterscreate-get
      parameters:
      - in: query
        name: base
      - in: query
        name: exclude
        description: String list (semicolon delimited)
      - in: query
        name: include
        description: String list (semicolon delimited)
      - in: query
        name: unsafe
      responses:
        200:
          description: OK
      tags:
      - Files
  /filters/{filters}:
    get:
      summary: Get Filters
      description: "Returns the fields included by the given filters, and the \"safeness\"
        of those filters.\n \nIt is not expected that this method will be consumed
        by many applications at runtime, it is provided to aid in debugging.\n \n{filters}
        can contain up to 20 semicolon delimited filters. Filters are obtained via
        calls to /filters/create, or by using a built-in filter.\n \nThis method returns
        a list of filters."
      operationId: returns-the-fields-included-by-the-given-filters-and-the-safeness-of-those-filters-it-is-not-expecte
      x-api-path-slug: filtersfilters-get
      parameters:
      - in: path
        name: filters
        description: String list (semicolon delimited)
      responses:
        200:
          description: OK
      tags:
      - Files